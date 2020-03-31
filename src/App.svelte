<script>
  import { Router, Route } from 'svelte-routing'
  import { fade } from 'svelte/transition';
  import Nav from './Nav.svelte'
  import Bio from './Bio.svelte'
  import Art from './Art.svelte'

  export let url = ""

  let nextVisible = true
  let navigating = false

  const handleOutroEnd = () => {
    console.log("outro end")
  }

  const handleIntroStart = () => {
    console.log("intro start")
  }
</script>

<main>
  <Router url="{url}">
    <Nav />
    <section class="content">
      <Route path="bio">
        <article in:fade={{delay: 500, duration: 400}} out:fade on:introstart={handleIntroStart} on:outroend={handleOutroEnd}>
          <Bio />
        </article>
      </Route>
      <Route path="art">
        <article in:fade={{delay: 500, duration: 400}} out:fade on:introstart={handleIntroStart} on:outroend={handleOutroEnd}>
          <Art />
        </article>
      </Route>
      <Route path="tech">
      </Route>
      <Route path="contact">
      </Route>
    <section>
  </Router>
</main>

<style>

  main {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    height: 100%;
  }

  article {
    position: absolute;
    padding-right: 20px;
  }

  .content {
    flex: 3;
    margin: 40px;
    padding: 20px;
    border: 1px solid black;
    overflow: scroll;
    position: relative;
  }
  
  .content::-webkit-scrollbar {
    display: none;
  }

  h1 {
    font-size: 30px;
  }

  p {
    font-size: 18px;
  }

</style>
