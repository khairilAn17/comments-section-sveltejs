<script>
  export let data = [];
</script>

<div class="card">
  <div class="counter">
    <button>+</button>
    <p>{data.count}</p>
    <button>-</button>
  </div>
  <div class="card-wrapper">
    <div class="card-header">
      <div class="card-header_left">
        <img
          class="img-avatar"
          src={data.comment
            ? "https://picsum.photos/40"
            : "https://random.imagecdn.app/40/40"}
          alt="avatar"
        />
        <p class="name">{data.name}</p>
        <p class="time">{data.time}</p>
      </div>
      <div class="reply">
        <img src="/images/Path.png" alt="reply" />
        Reply
      </div>
    </div>
    <p>
      {data.text}
    </p>
  </div>
  <div />
</div>

<style>
  .card {
    display: flex;
    flex-direction: row;
    padding: 20px 20px;
    background-color: white;
    border-radius: 8px;
    margin-top: 20px;
  }
  .counter {
    height: 100%;
    width: 50px;
    margin: 0;
    text-align: center;
    padding: 10px;
    background-color: #f5f6fa;
    border-radius: 10px;
    font-size: 1.2rem;
  }
  button {
    margin: 0;
  }
  .counter :nth-child(2) {
    color: #5357b6;
    font-weight: 500;
    margin: 0;
  }
  .counter > button {
    border: none;
    color: #c5c6ef;
    background-color: #f5f6fa;
    font-weight: bold;
    font-size: 30px;
  }
  .counter > button:hover {
    color: #5357b6;
  }
  .card-header,
  .card-header_left {
    display: flex;
    align-items: center;
  }
  .card-header {
    justify-content: space-between;
  }
  .card-header_left > img,
  p {
    margin-left: 10px;
  }
  .img-avatar {
    border-radius: 50%;
  }
  .name {
    font-size: 1rem;
    font-weight: bold;
  }
  .reply {
    color: #5357b6;
    font-weight: bold;
  }
  .card-wrapper {
    width: 100%;
  }
  .card-wrapper > p {
    margin-top: 20px;
    font-size: 1rem;
    line-height: 24px;
  }
</style>
