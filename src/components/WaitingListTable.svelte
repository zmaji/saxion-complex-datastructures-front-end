<script>
    import WaitingListTableRow from "./WaitingListTableRow.svelte";

    export let waitingList = [];
</script>

<table class="table table-responsive table-striped caption-top">
    <caption>List of clients</caption>
    <thead>
    <tr class="table-dark">
        <th scope="col">ClientID</th>
        <th scope="col">Name</th>
        <th scope="col">Initials</th>
        <th scope="col">Urgency</th>
        <th scope="col">Number of Rooms</th>
        <th scope="col">Garden</th>
    </tr>
    </thead>
    <tbody>
    {#each waitingList as client}
        <WaitingListTableRow {client}/>
    {/each}
    </tbody>
</table>

<style>
    thead {
        position: sticky;
        top: 5rem;
    }
</style>