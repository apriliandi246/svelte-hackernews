<script>
   export let segment;
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

   a {
      color: #ffffff;
      text-decoration: none;
   }

   .underline {
      padding-bottom: 6px;
      border-bottom: 3px solid #ffffff;
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

      .underline {
         padding-bottom: 6.8px;
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
</style>

<nav class="navbar">
   <a href="/" class="navbar__brand" rel="prefetch"> HACKER NEWS </a>

   <ul>
      <li>
         <a
            href="newest"
            rel="prefetch"
            class:underline={segment === 'newest'}>newest</a>
      </li>
      <li>
         <a
            href="show"
            rel="prefetch"
            class:underline={segment === 'show'}>show</a>
      </li>
      <li>
         <a
            href="jobs"
            rel="prefetch"
            class:underline={segment === 'jobs'}>jobs</a>
      </li>
   </ul>
</nav>
