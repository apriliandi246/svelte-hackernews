<script>
   import { onDestroy, onMount } from "svelte";
   import Spinner from "../shared/Spinner.svelte";

   let jobs;
   const controller = new AbortController();

   onMount(async () => {
      const res = await fetch("https://node-hnapi.herokuapp.com/jobs", {
         signal: controller.signal,
      });
      jobs = await res.json();
   });

   onDestroy(() => {
      controller.abort();
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

   .data__time-ago {
      margin-top: 10px;
   }
</style>

{#if jobs === undefined}
   <Spinner />
{:else}
   {#each jobs as job (job.id)}
      <div class="data">
         <a href={job.url} target="_blank" class="data__title">{job.title}</a>
         <span class="data__url">{job.domain}</span>
         <br />
         <span class="data__time-ago">{job.time_ago}</span>
      </div>
   {/each}
{/if}
