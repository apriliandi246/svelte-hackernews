<script context="module">
   export async function preload() {
      const res = await this.fetch("https://node-hnapi.herokuapp.com/news");
      const allNews = await res.json();

      return { allNews };
   }
</script>

<script>
   import News from "../components/News/index.svelte";
   export let allNews;
</script>

<News {allNews} />
