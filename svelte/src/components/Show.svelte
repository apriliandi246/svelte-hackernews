<script>
   import { onMount } from "svelte";
   import Data from "./Data.svelte";
   import Spinner from "./Spinner.svelte";

   let allShow;

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/show");
      allShow = await res.json();
   });
</script>

{#if allShow === undefined}
   <Spinner />
{:else}
   {#each allShow as show (show.id)}
      <Data data={show} />
   {/each}
{/if}
