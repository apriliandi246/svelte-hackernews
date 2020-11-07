<script context="module">
   export async function preload() {
      const res = await this.fetch("https://node-hnapi.herokuapp.com/show");
      const allShow = await res.json();

      return { allShow };
   }
</script>

<script>
   import Data from "$components/Data.svelte";
   export let allShow;
</script>

{#each allShow as show (show.id)}
   <Data data={show} />
{/each}
