<script lang="ts">
    import { Link } from "svelte-routing";
    let open: boolean = false
    const onClick = () => open = !open
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
    .line {
        width: 35px;
        height: 5px;
        background-color: black;
        margin: 6px 0 0 0;
        transition: all 320ms ease;
        transform-origin: left; 
    }
    .line1 {
        transform: rotate(45deg) translate(0px, 1px);;
        background-color: #F5DF4D;
        
    }
    .line2 {
        opacity: 0
    }
    .line3 {
        transform: rotate(-45deg) translate(-3px, 2px);;
        background-color: #F5DF4D;
    }
    .hamburger {
        cursor: pointer;
        background: transparent;
        outline: none;
        border: none;
        position: absolute;
        top: 15px;
        left: 15px;
        z-index: 99;
    }
     
</style>

<nav>
    <div class="navbar">
        <button on:click={onClick} class="hamburger">
            <div class="line" class:line1={open}/>
            <div class="line" class:line2={open}/>
            <div class="line" class:line3={open}/>
        </button>
    </div>
    <div class="menu" class:open={open} class:closed={!open}>
        <Link on:click={onClick} to="/">Home</Link>
        <Link on:click={onClick} to="paintings">Paintings</Link>
    </div>

</nav>