<script>
    import { fade } from 'svelte/transition';

    export let client = {};
</script>

<tr transition:fade>
    <td>{client.id}</td>
    <td>{client.name}</td>
    <td>{client.initials}</td>
    <td>{client.urgency}</td>
    <td>{client.nrOfRooms}</td>
    <td>{@html client.garden.toString() === "true" ? `<i class="far fa-check-square text-success" style="font-size: 1.5rem"></i>` : `<i class="far fa-times-circle text-danger" style="font-size: 1.5rem"></i>`}</td>
</tr>
