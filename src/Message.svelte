<script>

    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();


  let message = "";
  let author = "";

  function saveMessage() {
    const newMessage = {
      id: Date.now(),
      text: message,
      author: author
    };
    
    console.log("newMessage", newMessage);
    dispatch('message', newMessage);
    message = "";
    author = "";
  }
</script>

<style></style>

<input type="text" bind:value={ author }>
<br>
<textarea cols="50" rows="5" bind:value={ message } />
<br>
<button on:click={ saveMessage }>send</button>
