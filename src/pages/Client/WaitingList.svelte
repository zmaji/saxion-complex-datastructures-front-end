<script>
    import WaitingListTable from "../../components/layout/Client/WaitingListTable.svelte";

    let waitingList = [];

    const fetchWaitingList = (async () => {
        const response = await fetch('http://localhost:8080/clients');
        const result = await response.json();
        waitingList = result;
        console.log(waitingList)

        return result;
    })();
</script>

{#await fetchWaitingList}
    <div class="alert alert-primary" role="alert">
        Fetching waiting list...
    </div>
{:then waitingList}
    {#if waitingList.length > 0 }
        <WaitingListTable {waitingList}/>
    {:else}
        <div class="alert alert-warning alert-dismissible fade show" role="alert">
            No waiting list found...
            <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
        </div>
    {/if}
{:catch error}
    <div class="alert alert-danger alert-dismissible fade show" role="alert">
        Failed to fetch waiting list...
        <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
    </div>
{/await}