<script>
   import Nav from "./components/Nav/index.svelte";
   import New from "./components/New/index.svelte";
   import Show from "./components/Show/index.svelte";
   import Jobs from "./components/Jobs/index.svelte";
   import News from "./components/News/index.svelte";

   let currentMenu = "news";

   function changeMenu(menu) {
      currentMenu = menu;
   }
</script>

<style>
   .container {
      width: 100%;
      margin: 0 auto;
   }

   .data-container {
      background-color: #f6f6ef;
      padding: 27px 14px;
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

<Nav {changeMenu} {currentMenu} />

<div class="container">
   <div class="data-container">
      {#if currentMenu === 'news'}
         <News />
      {:else if currentMenu === 'new'}
         <New />
      {:else if currentMenu === 'show'}
         <Show />
      {:else}
         <Jobs />
      {/if}
   </div>
</div>
