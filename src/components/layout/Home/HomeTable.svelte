<script>
    import HomeTableRow from "./HomeTableRow.svelte";

    export let homes = [];
</script>

<table class="table table-responsive table-striped caption-top">
    <caption>List of homes</caption>
    <thead>
    <tr class="table-dark">
        <th scope="col">HomeID</th>
        <th scope="col">AddressX</th>
        <th scope="col">AddressY</th>
        <th scope="col">Rent</th>
        <th scope="col">NrOfRooms</th>
        <th scope="col">Garden</th>
    </tr>
    </thead>
    <tbody>
        {#each homes as home}
            <HomeTableRow {home}/>
        {/each}
    </tbody>
</table>

<style>
    thead {
        position: sticky;
        top: 5rem;
    }
</style>