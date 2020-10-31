<script>
   export let status;
   export let error;

   const dev = process.env.NODE_ENV === "development";
</script>

<style>
   h1 {
      font-size: 2.8em;
      font-weight: 700;
      margin-bottom: 20px;
      letter-spacing: 4px;
      font-family: monospace;
   }

   p {
      font-size: 20px;
      padding-bottom: 135px;
      font-family: monospace;
   }

   main {
      margin-top: 100px;
      text-align: center;
   }

   @media (min-width: 480px) {
      h1 {
         font-size: 4em;
      }
   }
</style>

<svelte:head>
   <title>{status}</title>
</svelte:head>

<main>
   <h1>{status}</h1>

   <p>{error.message}</p>

   {#if dev && error.stack}
      <pre>{error.stack}</pre>
   {/if}
</main>
