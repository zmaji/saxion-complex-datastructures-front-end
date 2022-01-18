<script>
    import { fade } from 'svelte/transition';

    export let qualifiedClientHome = {};
</script>

<tr transition:fade>
    <td>{qualifiedClientHome.client.id}</td>
    <td>{qualifiedClientHome.client.name}</td>
    <td>{qualifiedClientHome.client.initials}</td>
    <td>{qualifiedClientHome.client.urgency}</td>
    <td>{qualifiedClientHome.client.nrOfRooms}</td>
    <td>{@html qualifiedClientHome.client.garden.toString() === "true" ? `<i class="far fa-check-square text-success" style="font-size: 1.5rem"></i>` : `<i class="far fa-times-circle text-danger" style="font-size: 1.5rem"></i>`}</td>
    <td>{qualifiedClientHome.home.homeID}</td>
</tr>
