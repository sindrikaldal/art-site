<script lang="ts">
    import { get } from 'svelte/store'
    import { Link } from "svelte-routing";
    import Hamburger from './Hamburger.svelte'

    let open = false;

    const onClick = () => open = !open;
 
</script>

<style type="text/scss">
    .menu {
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        background-color: grey;
        overflow-x: hidden;
        height: 100%;
        width: 100%;
        position: fixed;
        top: 0; 
        opacity: 0;
    }
    .menu :global(a) {
        opacity: 0;
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
        animation: fadeIn 0.5s ease-in-out forwards;
    }
    .open :global(a) {
        animation: fadeIn 0.5s ease-in-out forwards 0.5s;
    } 
    .closed {
        animation: fadeOut 0.5s ease-in-out forwards;
    }


    @keyframes fadeIn {
        0% {
            opacity: 0;
            z-index: -1;
        }
        100% {
            opacity: 1;
            z-index: 1;
        }
    }

    @keyframes fadeOut {
        0% {
            opacity: 1;
            z-index: 0;
        }
        100% {
            opacity: 0;
            z-index: -1;
        }
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