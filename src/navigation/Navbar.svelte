<script lang="ts">
    import { get } from 'svelte/store'
    import { Link } from "svelte-routing";
    import Hamburger from './Hamburger.svelte'

    let open = false;

    const onClick = (open) => open = !open;
 
</script>

<style>
    .menu {
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        background-color: grey;
        transition: opacity 320ms ease;
        height: 100vh;
        width: 100%;
        position: absolute;
        top: 0;
    }
    .menu :global(a) {
        opacity: 0;
        transition: opacity 320ms ease;
        font-size: clamp(
            var(--fluid-type-min, 3rem),
            calc(3rem + var(--fluid-type-target, 7vw)),
            var(--fluid-type-max, 10rem)
        );
        margin-bottom:5px;
        color: #F5DF4D;
    } 
    .menu :global(a):hover {
        color: pink;
    } 
    .navbar {
        width: 100%;
        height: 100px;
    }
    .open {
        opacity: 1;
        z-index:1;
    }
    .open :global(a) {
        opacity: 1;
        transition-delay: 320ms;
        
    } 
    .closed {
        opacity: 0;
        z-index: -1;
    }
</style>

<nav>
    <div class="navbar">
        <Hamburger bind:open={open} />
    </div>
    <div class="menu" class:open={open} class:closed={!open}>
        <Link on:click={onClick} to="/">Home</Link>
        <Link on:click={onClick} to="paintings">Paintings</Link>
    </div>
</nav>