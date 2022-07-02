<script>
    export let id;

    const handleMouseEnter = () => {
        console.log(id);
    }

</script>

<week-slot on:mouseenter={handleMouseEnter}>
    <week {id}/>
</week-slot>


<style>
    week-slot {
        position: relative;
        display: flex;
        border: solid red 1px;
    }

    week {
        flex: 1;
        left: 4px;
        top: 4px;
        margin: 10%;
        display: inline-block;
        border: solid black 1px;
        background-color: gray;
        border-radius: 8px;
        aspect-ratio: 1;
    }

    week-slot:hover > week {
        filter: brightness(1.5);
    }

</style>