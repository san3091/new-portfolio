<script>
  import { fade } from 'svelte/transition'
  import Work from './components/Work.svelte'
  const me = {
    title: "Queer dancer tech witch musician based in Chicago, IL",
    description: "<p>I'm currently the lead engineer for <a href='https://catalyticsound.com/''>Catalytic Sound</a> and dance for <a href='https://www.luckyplush.com/''>Lucky Plush Productions</a>. I love diagrams and structures and explore them through dance, machine learning, music, electronics, improvisation of all kinds, installation art, and all the intersections thereof.</p><p>Follow my work on on <a href='https://www.instagram.com/santiago_mvmt/'>instagram</a>, and watch some of it on <a href='https://vimeo.com/santiagoqg'>vimeo</a>.</p>",
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
