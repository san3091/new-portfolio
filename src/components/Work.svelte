<script>
  import { fade } from 'svelte/transition';
  export let header
  export let body
</script>

<div in:fade={{delay: 1000, duration: 400}} out:fade>
  <h2>{header}</h2>
  <p>{body}</p>
</div>

<style>
</style>