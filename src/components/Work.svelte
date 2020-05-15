<script>
  import { fade } from 'svelte/transition';
  export let header
  export let body
  export let mediaWidth = '65%'
</script>

<div 
  class='work'
  style='--media-width: {mediaWidth}'
  in:fade={{delay: 700, duration: 500}} out:fade>
  <div class='media'>
  </div>
  <div class='text'>
    <h2>{header}</h2>
    <p>{@html body}</p>
  </div>
</div>

<style>
  .work {
    display: flex;
    flex-direction: row;
    flex: 1;
    width: 100%;
    padding: 20px 0;
  }

  .media {
    min-width: var(--media-width);
    box-sizing: border-box;
    padding: 20px;
    border-right: 1px solid black;
  }

  .text {
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
</style>