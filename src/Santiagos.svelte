<script>
  import { onMount } from 'svelte'
  import { fade } from 'svelte/transition'
  import { Link } from 'svelte-routing'

  // import PhotoCarousel from './components/PhotoCarousel.svelte'
  let height
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


<div class="slideshow"
  in:fade={{delay: 400, duration: 800}}
  bind:clientHeight={height}
  style='--photo-height:{height * 0.85}px'>
  <div class="back">
    <Link to="night-of-1000-santiagos">Get me out of here</Link>
  </div>
  <div class="slideshow-container">
    {#each photos as src}
      <div class="slideshow-item">
        <img transition:fade {src} alt="" />
      </div>
    {/each}
  </div>
</div>

<style>
  .back {
    margin-left: 60px;
    padding: 20px 0;
    text-decoration: underline;
  }

  .slideshow {
    overflow: scroll;
    margin: 10px;
    display: flex;
    flex-direction: column;
  }

  .slideshow-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  .slideshow-item {
    height: var(--photo-height);
    margin: 10px;
  }

  img {
    max-height: 100%;
  }

</style>
