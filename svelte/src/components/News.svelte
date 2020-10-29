<script>
   import { onMount } from "svelte";
   import Data from "./Data.svelte";
   import Spinner from "./Spinner.svelte";

   let allNews;

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/news");
      allNews = await res.json();
   });
</script>

{#if allNews === undefined}
   <Spinner />
{:else}
   {#each allNews as news (news.id)}
      <Data data={news} />
   {/each}
{/if}
