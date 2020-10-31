<script>
   import Nav from "../components/Nav/index.svelte";
   export let segment;
</script>

<style>
   .container {
      width: 100%;
      margin: 0 auto;
   }

   .data-container {
      background-color: #f6f6ef;
      padding: 28px 14px;
   }

   @media screen and (min-width: 940px) {
      .container {
         width: 90%;
      }
   }

   @media screen and (min-width: 1020px) {
      .container {
         width: 85%;
      }
   }

   @media screen and (min-width: 1270px) {
      .container {
         width: 76%;
      }
   }

   @media screen and (min-width: 1570px) {
      .container {
         width: 70%;
      }
   }
</style>

<Nav {segment} />

<div class="container">
   <div class="data-container">
      <slot />
   </div>
</div>
