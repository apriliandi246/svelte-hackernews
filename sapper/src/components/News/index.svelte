<script>
   import Data from "../shared/Data.svelte";
   import Spinner from "../shared/Spinner.svelte";

   export let allNews;

   // const controller = new AbortController();

   // onDestroy(() => {
   //    controller.abort();
   // });
</script>

{#if allNews === undefined}
   <Spinner />
{:else}
   {#each allNews as news (news.id)}
      <Data data={news} />
   {/each}
{/if}
