<script>
  import { Router, link } from 'svelte-routing'
  import { onMount } from 'svelte'
  import { fly } from 'svelte/transition'
  import NavLink from './NavLink.svelte'

  onMount(() => {
    visible = true
  })

  let visible = false
</script>

<nav>
  {#if visible}
    <div transition:fly="{{x: -200, duration: 800}}">
      <NavLink to="/" header="{true}">
        <h1>Santiago<br>Quintana</h1>
      </NavLink>
    </div>
    <div transition:fly="{{x: -200, duration: 1000}}">
      <NavLink to="bio">Bio</NavLink>
    </div>
    <div transition:fly="{{x: -200, duration: 1200}}">
      <NavLink to="art">Art</NavLink>
    </div>
    <div transition:fly="{{x: -200, duration: 1400}}">
      <NavLink to="tech">Tech</NavLink>
    </div>
    <div transition:fly="{{x: -200, duration: 1600}}">
      <NavLink to="contact">Contact</NavLink>
    </div>
  {/if}
</nav>

<style>
  nav {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-left: 70px;
    text-align: right;
  }

  div {
    margin-bottom: 15px;
  }
  
</style>
