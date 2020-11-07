<script context="module">
   export async function preload() {
      const res = await this.fetch("https://node-hnapi.herokuapp.com/newest");
      const allNew = await res.json();

      return { allNew };
   }
</script>

<script>
   import Data from "$components/Data.svelte";
   export let allNew;
</script>

{#each allNew as newest (newest.id)}
   <Data data={newest} />
{/each}
