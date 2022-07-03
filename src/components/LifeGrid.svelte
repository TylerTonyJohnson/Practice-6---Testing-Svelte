<script>
    import Week from "./Week.svelte";
    import RibbonLabel from "./RibbonLabel.svelte";

    let gridWidth = 10;
    let gridHeight = 8;
    $: weekCount = gridWidth * gridHeight;
    let rootDate;

    let color = "#B04F4F";

</script>


<main>
    <controls>
        <input type="color" bind:value={color} />
        <div>
            <label for={gridWidth}>{gridWidth}</label>
            <input type="range" bind:value={gridWidth} min="1" max="52" />
        </div>
        <div>
            <label for={gridHeight}>{gridHeight}</label>
            <input type="range" bind:value={gridHeight} min="1" max="77" />
        </div>
        <input type="date" bind:value={rootDate} />
    </controls>
    <gridContainer>
        <lifeGrid style="--grid-width: {gridWidth}">
            {#each Array(weekCount) as item, id}
                <Week id={id + 1} color={color}/>
            {/each}
        </lifeGrid>
        <RibbonLabel length={gridWidth} location="month-label"></RibbonLabel>
        <RibbonLabel length={gridHeight} location="year-label"></RibbonLabel>
    </gridContainer>
</main>


<style>

    controls {
        margin: auto;
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    gridContainer {
        display: grid;
        grid-template-columns: auto minmax(0, 1fr);
        grid-template-rows: auto minmax(0, 1fr);
        grid-template-areas: "space month-label" "year-label life-grid";
        width: 100%;
        border: solid blue 1px;
    }

    lifeGrid {
        --grid-width: 10;
        grid-area: life-grid;
        /* flex: 1; */
        background-color: var(--grid-color);
        display: grid;
        grid-template-columns: repeat(var(--grid-width), 1fr);
        border: solid green 1px;
        width: 100%;
    }
</style>