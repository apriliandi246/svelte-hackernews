<script>
   import { onDestroy, onMount } from "svelte";
   import Data from "./Data.svelte";
   import Spinner from "./Spinner.svelte";

   let allShow;
   const controller = new AbortController();

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/show", {
         signal: controller.signal,
      });
      allShow = await res.json();
   });

   onDestroy(() => {
      controller.abort();
   });
</script>

{#if allShow === undefined}
   <Spinner />
{:else}
   {#each allShow as show (show.id)}
      <Data data={show} />
   {/each}
{/if}
