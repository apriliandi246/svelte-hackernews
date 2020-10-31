<script context="module">
   export async function preload() {
      const res = await this.fetch("https://node-hnapi.herokuapp.com/show");
      const allShow = await res.json();

      return { allShow };
   }
</script>

<script>
   import Show from "../../components/Show/index.svelte";
   export let allShow;
</script>

<Show {allShow} />
