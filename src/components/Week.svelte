<script>
    export let id;
    export let color = "gray";
    const handleMouseEnter = () => {
        console.log(id);
    }

</script>

<week-slot on:mouseenter={handleMouseEnter}>
    <week id={id} style="--color: {color}"/>
</week-slot>


<style>
    week-slot {
        position: relative;
        display: flex;
        /* border: solid red 1px; */
    }

    week {
        --color: none;
        flex: 1;
        /* left: 4px; */
        /* top: 4px; */
        margin: 10%;
        /* display: inline-block; */
        border: solid black 1px;
        background-color: var(--color);
        border-radius: 20%;
        aspect-ratio: 1;
    }

    week-slot:hover > week {
        /* filter: brightness(1.5); */
        background-color: white;
    }

</style>