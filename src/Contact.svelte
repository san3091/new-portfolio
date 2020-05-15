<script>
  import { fade } from 'svelte/transition'

  let name, email, message, honeypot, errorMessage
  let messageSent = false
  let sending = false

  const setErrorMessage = () => {
    let newMessage = []
    if (!name) { newMessage.push('name is required')}
    if (!email) { newMessage.push('email is required')}
    if (!message) { newMessage.push('message is required')}

    errorMessage = newMessage.join(', ')
  }

  const submitForm = (e) => {
    e.preventDefault()
    if (name && email && message && !honeypot && !sending) {
      sending = true
      var url = 'https://script.google.com/macros/s/AKfycbzRZDcDygipswfktZnpvNlzkZr95KF2YgPocqwkQg/exec'
      var xhr = new XMLHttpRequest()
      xhr.open('POST', url)
      xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded")
      xhr.onreadystatechange = () => {
        if (xhr.readyState === 4 && xhr.status === 200) {
          messageSent = true
        } else if (xhr.status !== 200) {
          errorMessage = 'oops, something went wrong'
        }
        sending = false
      }
      xhr.send(JSON.stringify({name, email, message}))
    } else {
      setErrorMessage()
    }
  }
</script>

<div id='contact' transition:fade>
  {#if !messageSent}
    <form>
        <input id='name' bind:value={name} type='text' name='name'>
        <label for='name'>Name</label>
        <input id='email' bind:value={email} type='email' name='email'>
        <label for='email'>Email</label>
        <input bind:value={honeypot} type="hidden" name='honeypot'>
        <textarea id='message' bind:value={message} name='message'></textarea>
        <label for='message' >Message</label>
      <button type='submit' name='submit'
        on:click={submitForm}>
        submit
      </button>
      {#if errorMessage}
        <p class='error-message'>{errorMessage}</p>
      {/if}
    </form>
  {/if}
</div>

<style>
 #contact {
    position: absolute;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;
    width: 100%;
  }
  
  form {
    display: flex;
    flex-direction: column;
    width: 500px;
  }

  label {
    margin: 0 0 10px;
  }

  input, textarea {
    border-radius: 0;
    border: none;
    border-bottom: 1px solid black;
    background-color: hsl(0, 0%, 98%);
  }

  textarea {
    height: 100px;
    resize: none;
  }

  button {
    margin-top: 10px;
    width: 100%;
    background-color: transparent;
    border: 1px solid black;
    height: 40px;
    transition: .5s;
  }

  button:hover {
    background-color: hsl(0, 0%, 97%);
  }

  .error-message {
    margin: auto;
    font-size: 14px;
    color: red;
  }
</style>