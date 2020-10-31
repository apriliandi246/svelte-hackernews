<script context="module">
   export async function preload() {
      const res = await this.fetch("https://node-hnapi.herokuapp.com/newest");
      const allNew = await res.json();

      return { allNew };
   }
</script>

<script>
   import New from "../../components/Newest/index.svelte";
   export let allNew;
</script>

<New {allNew} />
