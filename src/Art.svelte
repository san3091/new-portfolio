<script>
  import Works from './components/Works.svelte'

  let uid = 1
  const art = [
    {
      id: uid++,
      route: "art/99",
      title: "99",
      description: `Presented at ADF. I created a model using a <a href="https://github.com/ibab/tensorflow-wavenet/" alt="Tensorflow Wavenet Github Repo" class="link">TensorFlow implementation of DeepMind's WaveNet paper</a>. I recorded myself reading passages from Virginia Wolf's <span class="underline">To The Lighthouse</span> and trained a model using a GPU EC2 instance on AWS. I trained the model for 99,999 iterations over the course of a week. I generated audio samples at different stages and used these audio samples to generate the final piece of music for the piece. The piece is a quartet, where each of the dancers/neurons takes on movement that I generated and interprets it at different stages, mapped onto a diagonal. The piece traces the non-linear nature of a machine learning model's training. Some checkpoints produce clearer vocalizations than others, seemingly "regressing" in the process, but those diversions are crucial pieces of the learning process.`,
      link: {
        video: "",
        thumbnail: "images/99-score.jpg",
      }
    },
    {
      id: uid++,
      route: "art/the_other_being",
      title: "The Other Being",
      description: `I built a 'dance spider' using an arduino and four infrared sensors. I plugged it into Ableton Live and created a piece of music that could be modulated and controlled using my body's proximity to the spider's legs. The two dancers (Florencia DeBrun and Cristina Lisot) created a duet that negotiates two different cultures and worldviews, exploring proximity to the unknown.`,
      link: {
        video: "",
        thumbnail: "",
      }
    },
    {
      id: uid++,
      route: "art/or_what",
      title: "Or What",
      description: "Inspired by the creative process of Noa Zuk and Ohad Fishof, I generated an electronic rhythmic sequence with ML Magenta in Ableton and produced movement to that structure. I wanted to explore desire and trepidation, the moment of confidently shooting your shit with your crush and the following insecurity and trepidation. The process of seduction as a codified structured and yet endlessly variating performance.",
      link: {
        video: "",
        thumbnail: "images/or-what-1.jpg",
      }
    },
    {
      id: uid ++,
      route: "art/is_it_you",
      title: "Is It You?",
      description: "Devised in collaboration with Charlotte Vail and Emily Soong. Is It You is a comical exploration of loneliness, friendship, online dating, and masculiinity.",
      link: {
        video: "https://player.vimeo.com/video/382508775",
        thumbnail: ""
      },
    },
    {
      id: uid++,
      route: "art/sestina",
      title: "Sestina",
      description: "A broader interpretation of the structures and processes that fascinate me. Devised in collaboration with Sam, sestina uses the European poetic form to generate a structure for both music and movement. The sestina works by using six end-words and rearranging them in a specific pattern (algorithm?) to generate the order for that next stanza. Sam and I generated different 'moods' as each 'end-word' and switched between them according to the sestina's order. This piece brought up topics around the disconnection and disjointedness that can come from the rigid structures that shape our life.",
      link: {
        video: "",
        thumbnail: "images/sestina-score.jpg"
      }
    },
    {
      id: uid++,
      route: "art/abac",
      title: "ABAC",
      description: "This piece draws from the ternary structure of the Sonata form in the classical period of music. At it's simplest it presents a theme (A) then a contrasting phrase (B) and then a recapitulation (A). The dancers side by side use gestures expressing anger, sensuality, concern, or sadness, growing each time further and further from the original gesture. tThe further from the origin the more chaotic the form, and the further away the dancers are. After reaching the depth of the recursive form, the dancers retrace their steps and come back to where they began. The music (also created by myself) follows this structure with a muted electronic beat that grows sharper as we work towards the middle of the form.",
      link: {
        video: "",
        thumbnail: ""
      }
    }
  ]
</script>

<div class='art'>
  <Works works={art} />
</div>

<style>
  .art {
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    padding: 20px;
    width: 100%;
    height: 100%;
    position: absolute;
  }
</style>
