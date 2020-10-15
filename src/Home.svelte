<script>
  import { fade } from 'svelte/transition'
  import Work from './components/Work.svelte'
  const me = {
    title: "Software engineer/dancer based in Chicago, IL",
    description: "<p>I'm currently the lead engineer for <a href='https://catalyticsound.com/''>Catalytic Sound</a>. At any given time I'm fine tuning my homelab, working on my infosec skills, redesigning this website for the 100th time, or knitting.</p>",
    media: "images/santiagoTechnicalWide.jpg"
  }
</script>

<Work
  header={me.title}
  body={me.description}
  media={me.media} />

<style>
  .bio {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 100px;
  }

  a {
    color: red;
  }

</style>
