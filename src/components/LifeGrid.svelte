<script>
    import Week from "./Week.svelte";

    let gridWidth = 52;
    let gridHeight = 70;
    let weekCount = gridWidth * gridHeight;

    let color = "#ffffff";

</script>

<input type="color" bind:value={color} />
<input type="range" bind:value={gridWidth} min="1" max="52" />
<main style="--grid-color: {color}; --grid-width: {gridWidth}">
    
    {#each Array(weekCount) as item, id}
        <Week id={id + 1} />
    {/each}
    
</main>


<style>

    main {
        --grid-width: 10;

        background-color: var(--grid-color);
        display: grid;
        grid-template-columns: repeat(var(--grid-width), 1fr);
        border: solid green 1px;
        width: 100%;
    }

</style>