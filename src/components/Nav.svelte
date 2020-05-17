<script>
  import { Router, link } from 'svelte-routing'
  import { onMount } from 'svelte'
  import { fly } from 'svelte/transition'
  import NavLink from './NavLink.svelte'

  export let navItems

  let visible = false
  let height, width
  let lineAngle = 190
  const calcDuration = (index) => 800 + index * 200
  const calcAngle = (height, width) => {
    return Math.atan2(-height, width) * (180 / Math.PI)
  }

  $: if (height && width) { visible = true }
  $: lineAngle = calcAngle(height, width)
</script>

<nav
  bind:clientHeight={height}
  bind:clientWidth={width} 
  style='--home-angle: {lineAngle}deg; --angle: {lineAngle + 90}deg;'>
  {#if visible}
    <div class='absolute-container'>
      <div class='page-links'>
        {#each navItems as navItem, index}
          <div 
            class='page-link' 
            transition:fly="{{x: -200, duration: calcDuration(index), delay: 600}}">
            <NavLink to={navItem.route} header="{navItem.isHeader}">
              {@html navItem.title}
            </NavLink>
          </div>
        {/each}
      </div>
    </div>
    <div class='absolute-container'>
      <div 
        class='home-link' 
        transition:fly="{{x: -200, duration: calcDuration(0)}}">
        <NavLink to='/' header={true}>
          <h1>Santiago Quintana</h1>
        </NavLink>
      </div>
    </div>
  {/if}
  <div class='border'></div>
  <svg width={width} height={height}>
    <line x1="0" y1={height} x2={width} y2="0" stroke="black" />
  </svg>
</nav>

<style>
  nav {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin: 40px 0 40px 40px;
    text-align: right;
    width: 250px;
  }

  h1 {
    position: relative;
    background-color: white;
    white-space: nowrap;
    padding: 0 10px;
  }

  .page-links {
    z-index: 1;
    transform: rotate(var(--angle));
    position: absolute;
    top: 50px;
    left: 10px;
    width: 145px;
  }
  
  .home-link {
    transform: rotate(var(--home-angle));
  }

  .page-link {
    margin-bottom: 15px;
    cursor: pointer;
    padding: 0 30px;
  }

  svg {
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
  }

  .absolute-container {
    position: absolute;
    display: flex;
    height: 100%;
    width: 100%;
    justify-content: center;
    align-items: center;
  }
</style>
