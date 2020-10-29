<script>
   export let changeMenu;
   let isShow = false;

   function showDropdown() {
      isShow = !isShow;
   }
</script>

<style>
   .navbar {
      justify-content: space-between;
      background-color: #f1642b;
      align-items: center;
      padding-right: 30px;
      padding-left: 30px;
      display: flex;
      height: 38px;
   }

   .navbar__brand {
      text-shadow: 0.5px 0.5px rgba(0, 0, 0, 0.3);
      font-weight: bolder;
      font-size: 1.3rem;
      color: #ffffff;
      cursor: pointer;
   }

   .dropdown__button {
      text-shadow: 0.5px 0.5px rgba(0, 0, 0, 0.3);
      background-color: #f1642b;
      font-family: monospace;
      box-sizing: border-box;
      font-weight: bolder;
      letter-spacing: 1px;
      font-size: 1.1rem;
      cursor: pointer;
      color: #ffffff;
      outline: none;
      border: none;
   }

   .dropdown__content {
      background-color: #f1642b;
      font-family: monospace;
      margin-right: 110px;
      position: absolute;
      font-size: 18px;
      margin-top: 6px;
      display: none;
      width: 160px;
      z-index: 1;
   }

   .dropdown__item {
      text-shadow: 0.5px 0.5px rgba(0, 0, 0, 0.3);
      text-decoration: none;
      padding: 12px 16px;
      text-align: left;
      display: block;
      color: #ffffff;
      float: none;
   }

   .dropdown__item:hover {
      cursor: pointer;
      text-decoration: underline;
   }

   .show {
      display: block;
   }

   @media screen and (min-width: 940px) {
      .dropdown__content {
         margin-left: -150px;
      }
   }
</style>

<nav class="navbar">
   <p class="navbar__brand" on:click={() => changeMenu('news')}>HACKER NEWS</p>

   <div class="dropdown">
      <button
         on:click={showDropdown}
         type="button"
         class="dropdown__button">Menu</button>

      <div class="dropdown__content" class:show={isShow}>
         <p class="dropdown__item" on:click={() => changeMenu('new')}>/new</p>
         <p class="dropdown__item" on:click={() => changeMenu('show')}>/show</p>
         <p class="dropdown__item" on:click={() => changeMenu('jobs')}>/jobs</p>
      </div>
   </div>
</nav>
