<script>
  import { fade } from 'svelte/transition'
</script>

<div class='bio-container'>
  <div class='bio' in:fade={{delay: 300, duration: 500}} out:fade>
    <p>I am a queer Mexican-American dancer, actor, musician, and web developer based in Chicago.</p>
    <p>I am very interested in algorithms, structures, and processes. I use these terms broadly, as I work in a variety of disciplines. The processes that sustain the creative process, the structures that shape our lives in society, the algorithms that allow the generation of audio using machine learning, but also the algorithm that creates the sestina as a poetic form.</p>
    <p>Underneath all my work is a negotioation of boundaries—human-computer, person-society, social-political, person-person. The very structures that limit me are creating me. My creations expand me and limit me. I create prosthetics, objects tangible and intangible that extend my self, and elements that infringe upon my self and shape me.</p>
    <p>This motivating/describing statement is intentionally vague because it manifests very differently in different mediums and even different projects.</p>
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

  @media only screen and (max-width: 1000px) {

    .bio {
      display: block;
      padding: 15px;
    }

    .bio-container {
      display: block;
    }
  }
</style>
