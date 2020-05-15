<script>
  import { fade } from 'svelte/transition';
  export let header
  export let body
  export let media
  export let mediaWidth = '65%'
</script>

<div
  class='work'
  style='--media-width: {mediaWidth}'
  in:fade={{delay: 700, duration: 500}} out:fade>
  <div class='media'>
    <img src={media} alt={header} />
  </div>
  <div class='text'>
    <h2>{header}</h2>
    <p>{@html body}</p>
  </div>
</div>

<style>
  img {
    width: 100%;
  }

  .work {
    display: flex;
    flex-direction: row;
    flex: 1;
    box-sizing: border-box;
    width: 100%;
    padding: 20px 0;
  }

  .media {
    min-width: var(--media-width);
    box-sizing: border-box;
    padding: 20px;
    border-right: 1px solid black;
    display: flex;
    flex: 1;
    justify-content: center;
    align-items: center;
  }

  img {
    object-fit: contain;
    flex: 1;
    max-height: 100%;
  }

  .text {
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
</style>
