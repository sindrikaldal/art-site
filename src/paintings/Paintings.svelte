<script lang="ts">
import Painting from "./Painting.svelte";
 let paintings: {
     src: string,
     name: string
 }[] = [{
     src: '/images/image1.jpg',
     name: 'image1'
 }, {
     src: '/images/image2.jpg',
     name: 'image2'
 }]
</script>

<style>
    .wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        padding: 0 100px;
        ;
    }
    .title {
        grid-column: 1 / -1;
        justify-self: center
    }
</style>

<div class="wrapper">
    <h1 class="title">Paintings</h1>
    {#each paintings as painting}
        <Painting src={painting.src} name={painting.name} /> 
    {/each}
</div>