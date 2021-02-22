<script lang="ts">
    export let url: string;
    export let name: string;
</script>

<style>
    .wrapper {
        display: flex;
        flex-direction: column;
    }
    .painting {
        width: 100px;
        height: 100px;
    }
</style>

<div class="wrapper">
    <img alt={"a painting called " + name} src={url} class="painting"/>
    <p class="title">{name}</p>
</div>
