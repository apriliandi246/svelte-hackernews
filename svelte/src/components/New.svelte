<script>
   import { onMount } from "svelte";
   import Spinner from "./Spinner.svelte";

   let allNew;

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/newest");
      allNew = await res.json();
   });
</script>

<style>
   .data__title {
      text-decoration: none;
      letter-spacing: 1px;
      font-size: 1.2rem;
      margin-right: 9px;
      line-height: 1.1;
      color: black;
   }

   .data {
      margin-bottom: 30px;
   }

   .data span {
      display: inline-block;
      font-size: 0.9rem;
      color: #889996;
   }

   .data__title:hover {
      text-decoration: underline;
   }

   .data__points {
      margin-top: 10px;
   }
</style>

{#if allNew === undefined}
   <Spinner />
{:else}
   {#each allNew as eachNew (eachNew.id)}
      <div class="data">
         <a
            href={eachNew.url}
            target="_blank"
            class="data__title">{eachNew.title}</a>
         <span class="data__url">{eachNew.domain}</span>
         <br />
         <span class="data__points">{eachNew.points} points |</span>
         <span class="data__user">by {eachNew.user} |</span>
         <span class="data__time-ago">{eachNew.time_ago} |</span>
         <span class="data__comments">{eachNew.comments_count} comments</span>
      </div>
   {/each}
{/if}
