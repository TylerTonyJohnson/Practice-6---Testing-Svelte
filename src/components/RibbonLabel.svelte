<script>
    export const Orientation = {
        VERT: "Vertical",
        HORZ: "Horizontal",
    }
    export let length = 1;
    export let location = "none";

</script>


<main style="grid-area: {location}">
    {#each Array(length) as item, i}
        <div>{i}</div>
    {/each}
</main>


<style>
    main {
        display:grid;
        /* border: solid orange 1px; */
    }

    div {
        display: block;
        margin: auto;
        border: solid teal 1px;
    }


</style>