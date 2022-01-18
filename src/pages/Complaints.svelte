<script>
    import ComplaintTable from "../components/ComplaintTable.svelte";

    let complaints = [];

    const fetchComplaints = (async () => {
        const response = await fetch('http://localhost:8080/complaints');
        const result = await response.json();
        complaints = result;
        console.log(complaints)

        return result;
    })();
</script>

{#await fetchComplaints}
    <div class="alert alert-primary" role="alert">
        Fetching complaints...
    </div>
{:then complaints}
    {#if complaints.length > 0 }
        <ComplaintTable {complaints}/>
    {:else}
        <div class="alert alert-warning alert-dismissible fade show" role="alert">
            No complaints found...
            <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
        </div>
    {/if}
{:catch error}
    <div class="alert alert-danger alert-dismissible fade show" role="alert">
        Failed to fetch complaints...
        <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
    </div>
{/await}