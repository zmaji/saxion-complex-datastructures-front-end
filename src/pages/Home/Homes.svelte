<script>
    import HomeTable from "../../components/layout/Home/HomeTable.svelte";

    let homes = [];

    const fetchHomes = (async () => {
        const response = await fetch('http://localhost:8080/homes');
        const result = await response.json();
        homes = result;
        console.log(homes)

        return result;
    })();
</script>

{#await fetchHomes}
    <div class="alert alert-primary" role="alert">
        Fetching homes...
    </div>
{:then homes}
    {#if homes.length > 0 }
        <HomeTable {homes}/>
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