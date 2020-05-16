<script>
  import { Router, link } from 'svelte-routing'
  import { onMount } from 'svelte'
  import { fly } from 'svelte/transition'
  import NavLink from './NavLink.svelte'

  export let navItems

  onMount(() => {
    visible = true
  })

  let visible = false

  const calcDuration = (index) => 800 + index * 200
</script>

<nav>
  {#if visible}
    {#each navItems as navItem, index}
      <div transition:fly="{{x: -200, duration: calcDuration(index)}}">
        <NavLink to={navItem.route} header="{navItem.isHeader}">
          {@html navItem.title}
        </NavLink>
      </div>
    {/each}
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
    cursor: pointer;
  }

</style>
