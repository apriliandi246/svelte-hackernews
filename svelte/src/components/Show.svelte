<script>
   import { onMount } from "svelte";
   import Spinner from "./Spinner.svelte";

   let allShow;

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/show");
      allShow = await res.json();
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

{#if allShow === undefined}
   <Spinner />
{:else}
   {#each allShow as show (show.id)}
      <div class="data">
         <a href={show.url} target="_blank" class="data__title">{show.title}</a>
         <span class="data__url">{show.domain}</span>
         <br />
         <span class="data__points">{show.points} points |</span>
         <span class="data__user">by {show.user} |</span>
         <span class="data__time-ago">{show.time_ago} |</span>
         <span class="data__comments">{show.comments_count} comments</span>
      </div>
   {/each}
{/if}
