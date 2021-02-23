<script lang="ts">

</script>

<style>
    .wrapper {
        margin: 0 200px;
        z-index: 0;
    }
    .wrapper > p {
        opacity: 0;
        text-align: left;
        animation: slideIn 1000ms ease forwards;
    }

    .wrapper > p:nth-child(2) {
        animation-delay: 800ms;
    }
    .wrapper > p:nth-child(3) {
        animation-delay: 1600ms;
    }

    @keyframes slideIn {
        0% {
            transform: translateX(-1000px);
            opacity: 0;
        }
        100% {
            transform: translateX(0);
            opacity: 1;
        }
    }
</style>

<main>
    <h1 class="title">Art by Kaldal</h1>
    <div class="wrapper">
        <p>
            Welcome to my art page.  
        </p>
        <p>
            This website was mainly created to test the framework Svelte but I decided to post my (not-so-good-but-getting-better) paintings here for anyone interested.
        </p>
        <p>
            Any possible future art stuff will be posted here. Stay tuned.
        </p>
    </div>
</main>

