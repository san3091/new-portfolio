<script>
  import List from './components/List.svelte'
  let uid = 1
  const work = [
    {
      id: uid ++,
      title: "Is It You?",
      description: "Devised in collaboration with Charlotte Vail and Emily Soong. Is It You is a comical exploration of loneliness, friendship, online dating, and masculiinity.",
      link: {
        video: "https://player.vimeo.com/video/382508775"
      },
    },
    {
      id: uid++,
      title: "second test this is long",
      description: "This is another test for a description let's see what it's all about",
      link: {}
    }
  ]
</script>

<List items={work} />



