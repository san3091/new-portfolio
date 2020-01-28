<script>
  import { Router, Route } from 'svelte-routing'
  import Nav from './Nav.svelte'
  import Bio from './Bio.svelte'


  export let url = ""
</script>

<main>
  <Router url="{url}">
    <Nav />
    <section>
      <Route path="bio">
        <p>Thing!</p>
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

  section {
    flex: 3;
  }

  h1 {
    font-size: 30px;
  }

  p {
    font-size: 18px;
  }

</style>
