<script>
    import { Link } from "svelte-routing";
    import { onMount } from "svelte";
    import TutorialCard from "../components/TutorialCard.svelte";

    onMount(() => {
        document.title = "Tutorials - SCU ACM Wiki";
    });

    let tutorials = [
        {
            name: "C",
            link: "tutorials/c",
            imgSrc: "https://upload.wikimedia.org/wikipedia/commons/1/19/C_Logo.png",
        },
        {
            name: "C++",
            link: "tutorials/cpp",
            imgSrc: "https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/ISO_C%2B%2B_Logo.svg/1200px-ISO_C%2B%2B_Logo.svg.png",
        },
        {
            name: "Python",
            link: "tutorials/python",
            imgSrc: "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1869px-Python-logo-notext.svg.png",
        },
        {
            name: "JavaScript",
            link: "tutorials/javascript",
            imgSrc: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-logo.png/640px-JavaScript-logo.png",
        },
        {
            name: "Eduroam",
            link: "tutorials/eduroam",
            imgSrc: "https://upload.wikimedia.org/wikipedia/commons/8/8a/0207a74a86c5255a9d6458e587f1e9e4-flat-wifi-icon-by-vexels.png",
        },
    ];
</script>

<main>
    <h1>Tutorials</h1>
    <div>
        {#each tutorials as tut}
            <TutorialCard
                name={tut["name"]}
                link={tut["link"]}
                imgSrc={tut["imgSrc"]}
            />
        {/each}
    </div>
</main>

<style>
    div {
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
    }
</style>
