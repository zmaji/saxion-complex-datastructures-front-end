<script>
    import { fade } from 'svelte/transition';

    export let home = {};
</script>

<tr transition:fade>
    <td>{home.homeID}</td>
    <td>{home.addressX}</td>
    <td>{home.addressY}</td>
    <td>€ {home.rent}</td>
    <td>{home.nrOfRooms}</td>
    <td>{@html home.garden.toString() === "true" ? `<i class="far fa-check-square text-success" style="font-size: 1.5rem"></i>` : `<i class="far fa-times-circle text-danger" style="font-size: 1.5rem"></i>`}</td>
</tr>
