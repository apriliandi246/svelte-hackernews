<script context="module">
   export async function preload() {
      const res = await this.fetch("https://node-hnapi.herokuapp.com/news");
      const allNews = await res.json();

      return { allNews };
   }
</script>

<script>
   import Data from "../components/Data.svelte";
   export let allNews;
</script>

{#each allNews as news (news.id)}
   <Data data={news} />
{/each}
