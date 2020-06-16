<script>
  import { onMount } from 'svelte'

  function preload(src) {
    return new Promise(function(resolve) {
      let img = new Image()
      img.onload = resolve
      img.src = src
    })
  }

  onMount(() => {

  })
</script>
