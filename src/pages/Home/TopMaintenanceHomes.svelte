<script>
    let homes = [];

    const fetchHomes = (async () => {
        const response = await fetch('http://localhost:8080/homes/top-maintenance');
        const result = await response.json();
        homes = result;

        return result;
    })();
</script>

{#await fetchHomes}
    <div class="alert alert-primary" role="alert">
        Fetching homes...
    </div>
{:then homes}
    {#if homes.length > 0 }
        <table class="table table-responsive table-striped caption-top">
            <caption>List of top maintenance homes</caption>
            <thead>
            <tr class="table-dark">
                <th scope="col">HomeID</th>
                <th scope="col">Total maintenance cost</th>
            </tr>
            </thead>
            <tbody>
            {#each homes as home}
                <tr>
                    <td>{home.homeID}</td>
                    <td>{home.totalMaintenanceCost}</td>
                </tr>
            {/each}
            </tbody>
        </table>
    {:else}
        <div class="alert alert-warning alert-dismissible fade show" role="alert">
            No homes found...
            <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
        </div>
    {/if}
{:catch error}
    <div class="alert alert-danger alert-dismissible fade show" role="alert">
        Failed to fetch homes...
        <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
    </div>
{/await}