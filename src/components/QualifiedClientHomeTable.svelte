<script>
    import QualifiedClientHomeRow from "./QualifiedClientHomeRow.svelte";

    export let qualifiedClientHomes = [];
</script>

<table class="table table-responsive table-striped caption-top">
    <caption>List of qualified client homes</caption>
    <thead>
    <tr class="table-dark">
        <th scope="col">ClientID</th>
        <th scope="col">Name</th>
        <th scope="col">Initials</th>
        <th scope="col">Urgency</th>
        <th scope="col">Number of Rooms</th>
        <th scope="col">Garden</th>
        <th scope="col">Qualified homeID</th>
    </tr>
    </thead>
    <tbody>
    {#each qualifiedClientHomes as qualifiedClientHome}
        <QualifiedClientHomeRow {qualifiedClientHome}/>
    {/each}
    </tbody>
</table>

<style>
    thead {
        position: sticky;
        top: 5rem;
    }
</style>