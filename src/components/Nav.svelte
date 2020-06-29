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
    <div class="header" transition:fly="{{x: -200, duration: calcDuration(0)}}">
      <NavLink to="/" header>
        <h1>Santiago<br>Quintana</h1>
      </NavLink>
    </div>
    <div class="items">
      {#each navItems as navItem, index}
        <div transition:fly="{{x: -200, duration: calcDuration(index + 1)}}">
          <NavLink to={navItem.route} header="{navItem.isHeader}">
            {@html navItem.title}
          </NavLink>
        </div>
      {/each}
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

  .items {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  div {
    margin-bottom: 15px;
    cursor: pointer;
  }

  @media only screen and (max-width: 1000px) {
    nav {
      align-items: center;
    }

    .items {
      flex-direction: row;
    }

    div {
      margin-bottom: 0;
      margin-right: 10px;
    }
  }

</style>
