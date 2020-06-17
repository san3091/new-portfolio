<script>
  import { onMount } from 'svelte'
  import { fade } from 'svelte/transition'
  // import PhotoCarousel from './components/PhotoCarousel.svelte'

  let photos = Array
    .from({ length: 40 }, (_, i) => i + 1)
    .map( number => `images/santiagos/${number}.jpg`)

  function preload(src) {
    return new Promise(function(resolve) {
      let img = new Image()
      img.onload = resolve
      img.src = src
    })
  }

  onMount(() => {
    photos.map(photoUrl => {
      preload(photoUrl)
    })
  })
</script>

<div class="slideshow" in:fade={{delay: 400, duration: 800}}>
  <!-- <PhotoCarousel carouselPhotos={photos} /> -->
  <div class="slideshow-container">
    {#each photos as src}
      <div class="slideshow-item">
        <img transition:fade {src} alt="" />
      </div>
    {/each}
  </div>
</div>

<style>
  .slideshow {
    height: 100%;
    overflow: hidden;
  }

  .slideshow-container {
    position: relative;
    margin-left: 80px;
    height: 100%;
    max-width: 100%;
    display: flex;
    justify-content: start;
    align-items: center;

  }

  .slideshow-item {
    height: 470px;
  }

  img {
    height: 100%;
  }

</style>
