<script>
   import Data from "../shared/Data.svelte";
   import Spinner from "../shared/Spinner.svelte";

   export let allNew;
</script>

{#if allNew === undefined}
   <Spinner />
{:else}
   {#each allNew as eachNew (eachNew.id)}
      <Data data={eachNew} />
   {/each}
{/if}
