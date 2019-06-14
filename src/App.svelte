<script>
  import Message from './Message.svelte'

  export let name;
  
  let messages = [];

  const addMessage = (event) => {
    console.log(event.detail);
    messages = [event.detail, ...messages];
    
  }
  
</script>

<style>
  h1 {
    color: purple;
  }

  .author {
    font-weight: bold;
    padding-bottom: 1em;
  }
</style>

<h1>{name}</h1>

<Message on:message={ addMessage } />

<div>
  <h2>Messages</h2>
  { #each messages as message }
    <div class="author">By { message.author }</div>
    <div>{ message.text }</div>
    <hr>
  { /each }
</div>

