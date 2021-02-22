<script lang="ts">    
    export let src: string;
    export let name: string;
</script>

<style>
    .image {
        grid-column: span 1;
        display: grid;
        flex-direction: column;
        padding: 10px;
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
