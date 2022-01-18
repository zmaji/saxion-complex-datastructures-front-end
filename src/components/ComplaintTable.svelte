<script>
    import ComplaintTableRow from "./ComplaintTableRow.svelte";

    export let complaints = [];
</script>

<table class="table table-responsive table-striped caption-top">
    <caption>List of complaints</caption>
    <thead>
    <tr class="table-dark">
        <th scope="col">ComplaintID</th>
        <th scope="col">Category</th>
        <th scope="col">Estimated time</th>
        <th scope="col">Actual time</th>
        <th scope="col">Other costs</th>
        <th scope="col">HomeID</th>
    </tr>
    </thead>
    <tbody>
    {#each complaints as complaint}
        <ComplaintTableRow {complaint}/>
    {/each}
    </tbody>
</table>

<style>
    thead {
        position: sticky;
        top: 5rem;
    }
</style>