<script>
    import QualifiedClientHomeTable from "../../components/layout/Client/QualifiedClientHomeTable.svelte";

    let qualifiedClientHomes = [];

    const fetchQualifiedClientHomes = (async () => {
        const response = await fetch('http://localhost:8080/clients/qualified');
        const result = await response.json();
        qualifiedClientHomes = result;
        console.log(qualifiedClientHomes)

        return result;
    })();
</script>

{#await fetchQualifiedClientHomes}
    <div class="alert alert-primary" role="alert">
        Fetching qualified client homes...
    </div>
{:then qualifiedClientHomes}
    {#if qualifiedClientHomes.length > 0 }
        <QualifiedClientHomeTable {qualifiedClientHomes}/>
    {:else}
        <div class="alert alert-warning alert-dismissible fade show" role="alert">
            No qualified client homes found...
            <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
        </div>
    {/if}
{:catch error}
    <div class="alert alert-danger alert-dismissible fade show" role="alert">
        Failed to fetch qualified client homes...
        <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
    </div>
{/await}