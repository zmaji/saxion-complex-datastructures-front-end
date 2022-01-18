<script>
    import { fade } from 'svelte/transition';

    export let complaint = {};
</script>

<tr transition:fade>
    <td>{complaint.complaintID}</td>
    <td>{complaint.category}</td>
    <td>{complaint.estimatedTime}</td>
    <td>{complaint.actualTime}</td>
    <td>€ {complaint.otherCosts}</td>
    <td>{complaint.homeID}</td>
</tr>
