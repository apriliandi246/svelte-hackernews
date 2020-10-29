<script>
   import { onMount } from "svelte";
   import Data from "./Data.svelte";
   import Spinner from "./Spinner.svelte";

   let allNew;

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/newest");
      allNew = await res.json();
   });
</script>

{#if allNew === undefined}
   <Spinner />
{:else}
   {#each allNew as eachNew (eachNew.id)}
      <Data data={eachNew} />
   {/each}
{/if}
