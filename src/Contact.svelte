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

  const submitForm = () => {
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

<div id='contact'
  transition:fade>
  <div >
    <h2>How might we.. work together?</h2>
  </div>
  {#if !messageSent}
    <form>
        <label for='name'>Name</label>
        <input id='name' bind:value={name} type='text' name='name'>
        <label for='email'>Email</label>
        <input id='email' bind:value={email} type='email' name='email'>
        <input bind:value={honeypot} type="hidden" name='honeypot'>
        <label for='message' >Message</label>
        <textarea id='message' bind:value={message} name='message'></textarea>
      <button type='submit' name='submit'
        on:click={submitForm}>
        submit
      </button>
      {#if errorMessage}
        <p>{errorMessage}</p>
      {/if}
    </form>
  {/if}
</div>

<style>
 #contact {
    position: absolute;
    height: 100%;
    width: 100%;
  }
  
  form {
    display: flex;
    flex-direction: column;
    /* align-items: flex-end;
    position: absolute; */
    width: 100%;
    /* margin-right: var(--margin);
    bottom: 0;
    right: 0; */
  }

  input, textarea {
    /* width: 70%;
    font-family: 'Montserrat';
    color: darkslategray; */
    /* background-color: transparent; */
    border-radius: 0;
  }

  textarea {
    height: 100px;
    resize: none;
  }

  button {
    margin: 0 0 var(--margin) 0;
    width: 70%;
    align-self: flex-end;
    /* opacity: 0; */
  }
</style>