<script>
    import NavItem from './NavItem.svelte';

    let isNavOpen = false; // used for mobile view
</script>

<nav>
    <button on:click={() => {isNavOpen = !isNavOpen;}} class="outline contrast">
        &#9776;
    </button>
    <div class:open={isNavOpen}>
        <NavItem name="Home" route="/"/>
        <NavItem name="Tutorials" route="/tutorials"/>
        <NavItem name="Academics" route="/academics"/>
        <NavItem name="Career" route="/career"/>
    </div>
</nav>

<style>
    div {
        flex-direction: row;
        display: inline-flex;
        position: relative;
    }
    button {
        display: none;
        border: none;
        box-shadow: none;
    }
    nav {
        flex-direction: column;
        display: flex;
        width: 50%;
        justify-content: center;
        align-items: flex-start;
        overflow-x: hidden;
        gap: 0;
    }
    @media (max-width: 576px) {
        div {
            flex-direction: column;
            display: none;
        }
        div.open {
            display: flex;
            background-color: #08347A;
        }
        button {
            display: flex;
            flex-direction: column;
            text-align: center;
        }
        nav {
            position: fixed;
            top: 0;
            right: 0;
            align-items: flex-end;
        }
    }
</style>