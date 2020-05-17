<script>
  import { Router, Route } from 'svelte-routing'
  import { fade } from 'svelte/transition';
  import Nav from './components/Nav.svelte'
  import Bio from './Bio.svelte'
  import Art from './Art.svelte'
  import Tech from './Tech.svelte'
  import Contact from './Contact.svelte'
  import Home from './Home.svelte'

  export let url = ""

  let nextVisible = true
  let navigating = false
  const navItems = [
    { route: 'bio',
      title: 'Bio'
    },
    {
      route: 'art',
      title: 'Art'
    },
    {
      route: 'tech',
      title: 'Tech'
    },
    {
      route: 'contact',
      title: 'Contact'
    }
  ]


</script>

<main>
  <Router url="{url}">
    <Nav navItems={navItems}/>
    <section class="content">
      <Route path="bio">
        <Bio />
      </Route>
      <Route path="art">
        <Art />
      </Route>
      <Route path="tech">
        <Tech />
      </Route>
      <Route path="contact">
        <Contact />
      </Route>
      <Route path="/">
        <Home />
      </Route>
    </section>
  </Router>
</main>

<style>

  :global(p) {
    line-height: 24px;
    font-size: 15px;
  }

  main {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    height: 100%;
    width: 100%;
  }

  .content {
    position: relative;
    display: flex;
    flex: 1;
    margin: 40px 40px 40px 0;
    border: 1px solid black;
    border-left: none;
    width: 100%;
  }

  .content::-webkit-scrollbar {
    display: none;
  }

</style>
