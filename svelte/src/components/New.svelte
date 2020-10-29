<script>
   import { onDestroy, onMount } from "svelte";
   import Data from "./Data.svelte";
   import Spinner from "./Spinner.svelte";

   let allNew;
   const controller = new AbortController();

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/newest", {
         signal: controller.signal,
      });
      allNew = await res.json();
   });

   onDestroy(() => {
      controller.abort();
   });
</script>

{#if allNew === undefined}
   <Spinner />
{:else}
   {#each allNew as eachNew (eachNew.id)}
      <Data data={eachNew} />
   {/each}
{/if}
