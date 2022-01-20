<script>
    import { fade } from 'svelte/transition';
    import HomeCard from "./HomeCard.svelte";

    export let homes;
</script>

<div class="row" transition:fade>
    {#each homes as home}
        <HomeCard {home}/>
    {/each}
</div>