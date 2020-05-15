<script>
  import { fly, fade } from 'svelte/transition'

  export let navItems
  export let selectedWork
  export let selectWork

  const calcDuration = (index) => 800 + index * 200
</script>

<nav>
  {#each navItems as navItem, index}
    <button 
      class:selected={navItem == selectedWork}
      in:fly="{{x: -200, duration: calcDuration(index)}}"
      out:fade
      on:click={() => { selectWork(navItem) }}>
        <h3>{navItem.title}</h3>
    </button>
  {/each}
</nav>

<style>
  nav {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    text-align: center;
    justify-self: flex-end;
    width: 80%;
    height: 64px;
  }

  h3 {
    font-size: 16px;
  }

  button {
    position: relative;
    border: none;
    background-color: transparent;
    transition: .5s;
    color: black;
  }

  button:hover {
    transform: translateY(-5px);
    cursor: pointer;
  }

  .selected, .selected:hover{
    transform: translateY(-15px);
    color: red;
  }
</style>
