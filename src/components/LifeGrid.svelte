<script>
    import Week from "./Week.svelte";
    
    let weekCount = 40;

</script>


<main>
    {#each Array(weekCount) as item}
        <Week/>
    {/each}
    
</main>


<style>
    main {
        display: grid;
        grid-template-columns: repeat(10, 1fr);
        border: solid green 1px;
        width: 100%;
    }

</style>