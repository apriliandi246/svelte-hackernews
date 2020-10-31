<script>
   import { onDestroy, onMount } from "svelte";
   import Data from "../shared/Data.svelte";
   import Spinner from "../shared/Spinner.svelte";

   let allNews;
   const controller = new AbortController();

   onMount(async () => {
      const res = await fetch(`https://node-hnapi.herokuapp.com/news`, {
         signal: controller.signal,
      });

      allNews = await res.json();
   });

   onDestroy(() => {
      controller.abort();
   });
</script>

{#if allNews === undefined}
   <Spinner />
{:else}
   {#each allNews as news (news.id)}
      <Data data={news} />
   {/each}
{/if}
