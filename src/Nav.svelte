<script>
  import { Router, link } from 'svelte-routing'
  import { onMount } from 'svelte'
  import { fly } from 'svelte/transition'

  onMount(() => {
    visible = true
  })

  let visible = false
</script>

<nav>
  {#if visible}
    <a href="/" use:link transition:fly="{{x: -200, duration: 800}}"><h1>Santiago<br>Quintana</h1></a>
    <a href="/bio" use:link transition:fly="{{x: -200, duration: 1000}}">Bio</a>
    <a href="/art" use:link transition:fly="{{x: -200, duration: 1200}}">Art</a>
    <a href="/tech" use:link transition:fly="{{x: -200, duration: 1400}}">Tech</a>
    <a href="/contact" use:link transition:fly="{{x: -200, duration: 1600}}">Contact</a>
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

  a {
    margin-bottom: 15px;
  }

  .active {
    margin-right: -5px;
    transition: margin-right 1s;
  }
</style>
