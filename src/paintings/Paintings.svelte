<script lang="ts">
import Painting from "./Painting.svelte";
 let paintings: {
     src: string,
     name: string
 }[] = [{
     src: '/images/painting-1.webp',
     name: 'Untitled #1'
 }, {
     src: '/images/painting-2.webp',
     name: 'Untitled #2'
 }]
</script>

<style type="text/scss">
    .wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        @media (min-width: 640px) {
            padding: 0 100px;
        }    
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