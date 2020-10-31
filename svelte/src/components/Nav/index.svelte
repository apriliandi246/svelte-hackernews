<script>
   export let changeMenu;
   export let currentMenu;
</script>

<style>
   .navbar {
      justify-content: space-between;
      flex-direction: column;
      justify-content: center;
      background-color: #ef482a;
      align-items: center;
      padding: 10px;
      display: flex;
   }

   .navbar__brand {
      text-shadow: 0.5px 0.5px rgba(0, 0, 0, 0.3);
      margin-bottom: 15px;
      font-weight: bolder;
      font-size: 1.3rem;
      color: #ffffff;
      cursor: pointer;
   }

   .navbar__brand:hover {
      text-decoration: underline;
   }

   ul {
      width: 60%;
      display: flex;
      color: #ffffff;
      cursor: pointer;
      align-items: center;
      justify-content: space-between;
   }

   li {
      font-size: 18px;
      font-weight: bold;
      letter-spacing: 1.3px;
      font-family: monospace;
   }

   li:hover {
      text-decoration: underline;
   }

   @media screen and (min-width: 1000px) {
      .navbar {
         flex-direction: row;
         align-items: center;
         justify-content: space-around;
      }

      .navbar__brand {
         margin-bottom: 0;
      }

      ul {
         width: 40%;
         justify-content: space-around;
      }
   }

   @media screen and (min-width: 1400px) {
      ul {
         width: 35%;
      }
   }

   @media screen and (min-width: 1700px) {
      ul {
         width: 27%;
      }
   }

   .underline {
      text-decoration: underline;
   }
</style>

<nav class="navbar">
   <h1
      class="navbar__brand"
      on:click={() => changeMenu('news')}
      class:underline={currentMenu === 'news'}>
      HACKER NEWS
   </h1>

   <ul>
      <li
         on:click={() => changeMenu('new')}
         class:underline={currentMenu === 'new'}>
         new
      </li>

      <li
         on:click={() => changeMenu('show')}
         class:underline={currentMenu === 'show'}>
         show
      </li>

      <li
         on:click={() => changeMenu('jobs')}
         class:underline={currentMenu === 'jobs'}>
         jobs
      </li>
   </ul>
</nav>
