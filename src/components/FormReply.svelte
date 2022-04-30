<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  let text = "";
  function onSubmit(e) {
    const formData = new FormData(e.target);
    let data = {};
    for (let field of formData) {
      const [key, value] = field;
      data[key] = value;
    }
    dispatch("add-comment", data);
    text = "";
  }
</script>

<div>
  <form action="" class="wrapper" on:submit|preventDefault={onSubmit}>
    <img
      class="img-avatar"
      src="https://random.imagecdn.app/40/40"
      alt="avatar"
    />
    <textarea
      name="text"
      id="text"
      cols="30"
      rows="10"
      bind:value={text}
      placeholder="Add a comment"
    />
    <button type="submit">SEND</button>
  </form>
</div>

<style>
  .wrapper {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    justify-content: space-between;
    padding: 20px 20px;
    background-color: white;
    border-radius: 8px;
    margin-top: 20px;
    padding: 20px 50px;
  }
  .img-avatar {
    border-radius: 50%;
  }
  textarea {
    width: 70%;
    padding: 10px;
    border: 1px solid #e9ebf0;
    border-radius: 10px;
    height: 100px;
    font-size: 1.2rem;
    font-family: "Rubik", sans-serif;
    resize: none;
  }
  textarea:focus {
    outline: none;
    font-family: "Rubik", sans-serif;
    font-size: 1.2rem;
  }
  button {
    background-color: #5357b6;
    color: white;
    width: 20%;
    height: 48px;
    border: none;
    font-size: 1.2rem;
    font-family: "Rubik", sans-serif;
    letter-spacing: 2px;
    border-radius: 8px;
  }
  button:active {
    background-color: #e9ebf0;
    color: #5357b6;
  }
</style>
