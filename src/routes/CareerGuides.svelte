<script lang="ts">
    import { marked } from "marked";
    import { onMount } from "svelte";

    let { name } = $props(); 
    let tutorial = $state("<p>file not found</p>");

    const renderer = {
        heading({ tokens, depth }) {
            const text = this.parser.parseInline(tokens);
            const escapedText = text.toLowerCase().replace(/[^\w]+/g, "-");

            return `
                <h${depth} id="${escapedText}">
                    ${text}
                </h${depth}>`;
        },
        link({ tokens, href }) {
            const text = this.parser.parseInline(tokens);
            const isExternalLink = !href.startsWith("#");
            const target = isExternalLink ? 'target="_blank"' : "";
            return `<a href="${href}" target="${target}">${text}</a>`;
        },
    };

    marked.use({ renderer });

    onMount(async () => {
        document.title = `${name.replace(/\b\w/g, (c: string) => c.toUpperCase())} - SCU ACM Wiki`;
        const response = await fetch("/career/"+ name + ".md");
        if (response.ok) {
            const responseContent = await response.text();
            if (responseContent.includes("<!doctype html>")) {
                console.error("Failed to fetch markdown file.");
                return;
            }
            tutorial = await marked.parse(responseContent);
        } else {
            console.error("Failed to fetch markdown file.");
        }
    });

    function handleLinkClick(event: MouseEvent) {
        const target = event.target as HTMLElement;
        if (
            target.tagName === "A" &&
            target.getAttribute("href")?.startsWith("#")
        ) {
            event.preventDefault();
            const id = target.getAttribute("href")?.substring(1);
            const element = document.getElementById(id);
            if (element) {
                element.scrollIntoView({ behavior: "smooth" });
            }
        }
    }
</script>

<svelte:window on:click={handleLinkClick} />

<div class="container">
    {@html tutorial}
</div>

<style>
    .container {
        margin: 2rem;
    }
</style>
