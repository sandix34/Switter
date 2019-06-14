<script>
  export let name;
  let message = "";
  let messages = [];

  function updateMessage(event) {
	console.log(event.target.value);
	message = event.target.value;
  }

  function saveMessage() {
    const newMessage= {
      id: Date.now(),
      text: message,
      author: 'Sandrine'
    };
    messages = [newMessage, ...messages]
    console.log('messages', messages );
    
  }
</script>

<style>
  h1 {
    color: purple;
  }
</style>

<h1>{name}</h1>
<textarea cols="50" rows="5" on:input={updateMessage} />
<br>
<button on:click={ saveMessage }>send</button>
<div>
	<h3>Preview</h3>
	{message}
</div>

