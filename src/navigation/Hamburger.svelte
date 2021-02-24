<script lang="ts">
    export let open;
    const onClick = () => open = !open;
</script>

<style type="text/scss">
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

<button on:click={onClick} class="hamburger">
    <div class="line" class:line1Out={open} class:line1In={!open}/>
    <div class="line" class:line2Out={open} class:line2In={!open}/>
    <div class="line" class:line3Out={open} class:line3In={!open}/>
</button>

