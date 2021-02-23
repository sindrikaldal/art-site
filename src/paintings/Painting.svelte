<script lang="ts">    
    export let src: string;
    export let name: string;
</script>

<style type="text/scss">
    .image {
        grid-column: 1 / -1;
        display: grid;
        flex-direction: column;
        justify-content: center;
        padding: 10px;
        @media (min-width: 640px) {
            grid-column: span 1;
        }
    }
    .title {
        grid-column: 1 / -1;
        color: black;
    }
    img {
        height: auto;
        width: 300px;
    }
</style>

<div class="image">
    <img src={src} alt=""/>
    <p class="title">{name}</p>
</div>
