<script>
	import {fade} from 'svelte/transition'

	export let carouselPhotos

	let index = 0

	const next = () => {
		index = (index + 1) % carouselPhotos.length
	}
</script>

<div class="container">
  {#each [carouselPhotos[index]] as src (index)}
    <img transition:fade {src} alt="" />
  {/each}
</div>

<button on:click={next}>onwards</button>

<style>
	img {
    object-fit: contain;
    position: absolute;
    height: 50%;
    max-width: 100%;
  }

  .container {
    border: 5px solid green;
    height: 300px;
    width: 500px;
  }
</style>

