<script>
  import Card from "./Card.svelte";
  import FormReply from "./FormReply.svelte";
  let comments = [
    {
      id: 1,
      name: "Budi anak Buk Ani",
      time: "1 minute ago",
      text: "Impressive! Though it seems the drag feature could be improved. But overall it looks incredible. You’ve nailed the design and the responsiveness at various breakpoints works really well.",
      count: 12,
      comment: true,
    },
  ];
  let replies = [];

  function addComment(e) {
    const { text } = e.detail;
    const newReply = {
      id: Math.floor(Math.random() * 10),
      name: "Khairil Anwar",
      time: "few seconds ago",
      text,
      count: 0,
      comments: false,
    };
    replies = [...replies, newReply];
  }
</script>

<div class="comment-section">
  {#each comments as data, id}
    <Card {data} />
  {/each}

  <div class="reply-section">
    {#each replies as data, id}
      <Card {data} />
    {/each}
  </div>
  <FormReply on:add-comment={addComment} />
</div>

<style>
  .comment-section {
    width: 50%;
    margin: 50px auto;
  }
  .reply-section {
    margin-top: 20px;
    margin-left: 50px;
    height: auto;
    border-left: 5px solid #979797;
    padding-left: 60px;
  }
</style>
