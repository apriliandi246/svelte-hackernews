<script context="module">
   export async function preload() {
      const res = await this.fetch("https://node-hnapi.herokuapp.com/jobs");
      const jobs = await res.json();

      return { jobs };
   }
</script>

<script>
   import Jobs from "../../components/Jobs/index.svelte";
   export let jobs;
</script>

<Jobs {jobs} />
