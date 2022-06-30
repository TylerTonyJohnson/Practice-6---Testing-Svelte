<script>

</script>

<week-slot>
    <week/>
</week-slot>

<style>
    week-slot {
        position: relative;
        display: flex;
        border: solid red 1px;
    }

    week {
        left: 4px;
        top: 4px;
        margin: 8px;
        display: inline-block;
        width: 20px;
        border: solid black 1px;
        background-color: blue;
        border-radius: 8px;
        aspect-ratio: 1;
    }

    week-slot:hover > week {
        transform: scale(1.5);
    }

</style>