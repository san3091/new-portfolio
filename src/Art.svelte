<script>
  import Works from './components/Works.svelte'

  let uid = 1
  const art = [
    {
      id: uid++,
      title: "Sonata no. 1",
      description: "This piece draws from the ternary structure of the Sonata form in the classical period of music. At it's simplest it presents a theme (A) then a contrasting phrase (B) and then a recapitulation (A). This project is currently in progress and will premiere at the Emergence Dance Festival organized by Alluvion Dance.",
      outLink: "",
      media: "images/sonata-1-score.jpg"
    },
    {
      id: uid++,
      title: "Sestina",
      description: "A broader interpretation of the structures and processes that fascinate me. Devised in collaboration with Sam, sestina uses the European poetic form to generate a structure for both music and movement. The sestina works by using six end-words and rearranging them in a specific pattern (algorithm?) to generate the order for that next stanza. Sam and I generated different 'moods' as each 'end-word' and switched between them according to the sestina's order. This piece brought up topics around the disconnection and disjointedness that can come from the rigid structures that shape our life.",
      outLink: "https://vimeo.com/401470006",
      media: "images/sestina-score.jpg"
    },
    {
      id: uid ++,
      title: "Is It You?",
      description: "Devised in collaboration with Charlotte Vail and Emily Soong. Is It You is a comical exploration of loneliness, friendship, online dating, and masculiinity.",
      media: "",
      outLink: "https://vimeo.com/382508775",
    },
    {
      id: uid++,
      title: "Or What",
      description: "Inspired by the creative process of Noa Zuk and Ohad Fishof, I generated an electronic rhythmic sequence with ML Magenta in Ableton and produced movement to that structure. I wanted to explore desire and trepidation, the moment of confidently shooting your shit with your crush and the following insecurity and trepidation. The process of seduction as a codified structured and yet endlessly variating performance.",
      media: "images/or-what-1.jpg",
      outLink: "https://vimeo.com/349680153"
    },
    {
      id: uid++,
      title: "99",
      description: `Presented at ADF. I created a model using a <a href="https://github.com/ibab/tensorflow-wavenet/" alt="Tensorflow Wavenet Github Repo" class="link">TensorFlow implementation of DeepMind's WaveNet paper</a>. I recorded myself reading passages from Virginia Wolf's <span class="underline">To The Lighthouse</span> and trained a model using a GPU EC2 instance on AWS. I trained the model for 99,999 iterations over the course of a week. I generated audio samples at different stages and used these audio samples to generate the final piece of music for the piece. The piece is a quartet, where each of the dancers/neurons takes on movement that I generated and interprets it at different stages, mapped onto a diagonal. The piece traces the non-linear nature of a machine learning model's training. Some checkpoints produce clearer vocalizations than others, seemingly "regressing" in the process, but those diversions are crucial pieces of the learning process.`,
      media: "images/99-score.jpg",
      outLink: "https://vimeo.com/349680536",
    },
    // {
    //   id: uid++,
    //   title: "Concentric",
    //   description: "",
    //   media: ""
    // }
  ]
</script>

<Works works={art} />
