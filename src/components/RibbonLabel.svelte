<script>
    export let length = 1;
    export let location = "none";
    export let orientation = "horizontal";

    const getOrientation = () => {
        switch (orientation) {
            case "vertical":
                return "row";
                break;
            case "horizontal":
                return "column";
                break;
        }
    }

</script>


<main 
    style="grid-area: {location};
    grid-auto-flow: {getOrientation()};
    grid-template-{getOrientation()}s: repeat({length}, 1fr);"
>
    {#each Array(length) as item, i}
        <div>{i % 5 === 0 ? i : ""}</div>
    {/each}
</main>


<style>
    main {
        display: grid;
        font-size: x-small;
        /* grid-auto-flow: column ; */
        /* justify-content: center;
        align-items: center; */
        /* border: solid orange 1px; */
    }

    div {
        display: block;
        margin: auto;
        border: solid teal 1px;
    }


</style>