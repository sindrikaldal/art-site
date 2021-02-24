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
        transform-origin: center;
        transition: all 320ms ease;
        
    }
    .line:not(:last-child) {
        margin: 0 0 8px 0;
    }
    .line1Out {
        animation: topLineOut 720ms ease forwards;
        background-color: #F5DF4D;
    }
    .line1In {
        animation: topLineIn 720ms ease forwards;
    }
    .line2In {
        animation: fadeIn 720ms ease forwards;
    }
    .line2Out {
        animation: fadeOut 720ms ease forwards;
    }
    .line3Out {
        animation: bottomLineOut 720ms ease forwards;     
        background-color: #F5DF4D;   
    }
    .line3In {
        animation: bottomLineIn 720ms ease forwards;        
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
    @keyframes topLineOut {
        0% {
            transform: translateY(0) rotate(0deg);
        }
        50% {
            transform: translateY(13px) rotate(0deg);
        }
        100% {
            transform: translateY(13px) rotate(-45deg);
        }
    }
    @keyframes topLineIn {
        0% {
            transform: translateY(13px) rotate(-45deg);
        }
        50% {
            transform: translateY(13px) rotate(0deg);
        }
        100% {
            transform: translateY(0);
        }
    }
    @keyframes bottomLineOut {
        0% {
            transform: translateY(0) rotate(0deg);
        }
        50% {
            transform: translateY(-13px) rotate(0deg);
        }
        100% {
            transform: translateY(-13px) rotate(45deg);
        }
    }

    @keyframes bottomLineIn {
        0% {
            transform: translateY(-13px) rotate(45deg);
        }
        50% {
            transform: translateY(-13px) rotate(0deg);
        }
        100% {
            transform: translateY(0);
        }
    }
    
    @keyframes fadeIn {
        0% {
            opacity: 0;
        }
        50% {
            opacity: 0;
        }
        100% {
            opacity: 1;
        }
    }
    @keyframes fadeOut {
        0% {
            opacity: 1;
        }
        25% {
            opacity: 0;
        }
        100% {
            opacity: 0;
        }
    }
     
</style>

<nav>
    <div class="navbar">
        <button on:click={onClick} class="hamburger">
            <div class="line" class:line1Out={open} class:line1In={!open}/>
            <div class="line" class:line2Out={open} class:line2In={!open}/>
            <div class="line" class:line3Out={open} class:line3In={!open}/>
        </button>
    </div>
    <div class="menu" class:open={open} class:closed={!open}>
        <Link on:click={onClick} to="/">Home</Link>
        <Link on:click={onClick} to="paintings">Paintings</Link>
    </div>

</nav>