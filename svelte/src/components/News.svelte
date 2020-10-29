<script>
   import { onMount } from "svelte";
   import Spinner from "./Spinner.svelte";

   let allNews;

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/news");
      allNews = await res.json();
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

{#if allNews === undefined}
   <Spinner />
{:else}
   {#each allNews as news (news.id)}
      <div class="data">
         <a href={news.url} target="_blank" class="data__title">{news.title}</a>
         <span class="data__url">{news.domain}</span>
         <br />
         <span class="data__points">{news.points} points |</span>
         <span class="data__user">by {news.user} |</span>
         <span class="data__time-ago">{news.time_ago} |</span>
         <span class="data__comments">{news.comments_count} comments</span>
      </div>
   {/each}
{/if}
