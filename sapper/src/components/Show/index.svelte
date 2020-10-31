<script>
   import Data from "../shared/Data.svelte";
   import Spinner from "../shared/Spinner.svelte";

   export let allShow;
</script>

{#if allShow === undefined}
   <Spinner />
{:else}
   {#each allShow as show (show.id)}
      <Data data={show} />
   {/each}
{/if}
