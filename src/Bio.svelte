<script>
  import { fade } from 'svelte/transition';
</script>

<div class='bio-container'>
  <div class='bio' in:fade={{delay: 300, duration: 500}} out:fade>
    <p>I am a queer Mexican dancer, actor, musician, and web developer based in Chicago. I trained in modern/contemporary dance at Beloit College in Beloit, WI. After graduation I attended a web development bootcamp and began my career in software engineering. My curiosity propelled me forward from an internship to a full time position, to consulting. After four years I was presented with the opportunity to dance as an understudy and then touring ensemble with Lucky Plush Productions. I took it. This steered my software career towards freelancing with small artistic non-profits who don't have the funds to hire an engineering team but have very real tech needs and revolutionary ideas.</p>
    <p>I am very interested in algorithms, structures, and processes. I use these terms broadly, as I work in a variety of disciplines. The processes that sustain the creative process, the structures that shape our lives in society, the algorithms that allow me to generate audio using machine learning, but also the algorith that gives us the sestina as a poetic form.</p>
    <p>Underneath all my work is an obsession with negotiating boundaries—human-computer, human-society, social-political, and interpersonal boundaries. As an immigrant I have been rubbing up against the edges of the American legal system for years. The frustration of being deeply restricted in what I can and cannot do for almost a decade has become deeply intertwined with my movement practice. A recognition also has dawned on me that the very structures that limit me are creating me, and pushing me to grow and develop in ways I wouldn't have otherwise. Working on holding both of these perspectives as true is one of the core sources of inspiration for my art.</p>
  </div>
</div>

<style>

  .bio {
    box-sizing: border-box;
    width: 100%;
    display: flex;
    flex: 1;
    flex-direction: column;
    justify-content: center;
    padding: 0 100px;
  }

  .bio-container  {
    position: absolute;
    height: 100%;
    display: flex;
  }
</style>
