<script>
  import { onMount } from 'svelte'
  import { fade } from 'svelte/transition'

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

<div class="party-container">
  <div class="description" in:fade={{delay: 300, duration: 500}} out:fade>
    <h1>The Night of One Thousand(ish) Santiagos</h1>
    <p>A costume party in this 27th of June of the year of our Lordess 2020, the 29th anniversary of his birth, celebrating that Santiago is old and is getting older, aging like a fine wine and giving no fucks.</p>
    <p>You have been chosen for a special homosexual celebration of Santiagos's first year in his thirtes. Because 29 is the first year of your thirties in the same way that 27 is the last year of your twenties and 28 is just kind of like a gap year. Anyway...</p>
    <h3>The theme is ME!</h3>
    <p>In these last 29 years I have shed a thousand skins and lived a thousand lives and I need them all with me to start this year. It is your quest to find them and bring them to me.</p>
    <ul class="list">
      <li>The nine summoned homosexuals shall have a soially distant hangout in my front yard, the address of which will be texted to you.</li>
      <li>You must come dressed as one of the many Santiagos that have seen the light of day.</li>
      <li>You are encouraged to bring your own beverages and a folding chair.</li>
      <li>I will be providing pre-sliced and plated snacks for optimal foodsharing with no contact.</li>
      <li>Should it rain, and to the comfort of those present, we will migrate indoors to my large living room and maintain socially distance ettiquette.</li>
    </ul>
    <p>For your pleasure and to jog your memory, I have assembled a collection of various santiagos with some brief details. I am also violently active on instagram and have documented every year of my life since 2012 there—feel free to roam.</p>
  </div>
</div>

<style>

  .list li {
    margin-bottom: 10px;
  }

  .description {
    box-sizing: border-box;
    width: 100%;
    display: flex;
    flex: 1;
    flex-direction: column;
    justify-content: center;
    padding: 0 100px;
  }

  .party-container  {
    position: absolute;
    height: 100%;
    display: flex;
  }
</style>
