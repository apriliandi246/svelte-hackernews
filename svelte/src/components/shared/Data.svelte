<script>
   export let data;
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

<div class="data">
   <a href={data.url} target="_blank" class="data__title">{data.title}</a>
   <span class="data__url">{data.domain}</span>
   <br />
   <span class="data__points">{data.points} points |</span>
   <span class="data__user">by {data.user} |</span>
   <span class="data__time-ago">{data.time_ago} |</span>
   <span class="data__comments">{data.comments_count} comments</span>
</div>
