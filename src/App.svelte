<script>
  import { Router, Route } from 'svelte-routing'
  import { fade } from 'svelte/transition';
  import Nav from './components/Nav.svelte'
  import Bio from './Bio.svelte'
  import Art from './Art.svelte'

  export let url = ""

  let nextVisible = true
  let navigating = false
  const navItems = [{
      route: '/',
      title: '<h1>Santiago <br> Quintana</h1>',
      isHeader: true
    },
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


  .content {
    position: relative;
    display: flex;
    flex: 1;
    margin: 40px;
    border: 1px solid black;
    width: 100%;
  }
  
  .content::-webkit-scrollbar {
    display: none;
  }

</style>
