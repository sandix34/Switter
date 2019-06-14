<script>
  let message = "";

  function saveMessage() {
    const newMessage = {
      id: Date.now(),
      text: message,
      author: "Sandrine"
    };
    //messages = [newMessage, ...messages];
    console.log("newMessage", newMessage);
    message = "";
  }
</script>

<style></style>

<textarea cols="50" rows="5" bind:value={ message } />
<br>
<button on:click={ saveMessage }>send</button>
