<script>
    import Week from "./Week.svelte";

    let gridWidth = 13;
    let gridHeight = 10;
    let weekCount = gridWidth * gridHeight;


</script>


<main>
    {#each Array(weekCount) as item, id}
        <Week {id}/>
    {/each}
    
</main>


<style>
    main {
        display: grid;
        grid-template-columns: repeat(13, 1fr);
        border: solid green 1px;
        width: 100%;
    }

</style>