<script>
  import { fade } from 'svelte/transition';
</script>

<div class='bio'>
  <div class='content' transition:fade>
    <p>I am a queer Mexican dancer, actor, musician, and web developer based in Chicago. I trained in modern/contemporary dance at Beloit College in Beloit, WI. Life then steered me to become a consultant web developer and work in that field for four years. After those four years it became possible for me to return to dance and performance as an understudy and then touring ensemble with Lucky Plush Productions. I attended ADF Summer Dance Intensive and began developing tools to generate movement with technology.</p>
    <p>I am very interested in algorithms, structures, and processes. I use these terms broadly, as I work in a variety of disciplines.</p>
    <p>Underneath all my work is a curiosity for cutting edge technology as well as an obsession with negotiating boundaries. As an immigrant I have been rubbing up against the edges of the American legal system for years. The frustration of being deeply restructed in what I can and cannot do for almost a decade has become deeply intertwined with my movement practice. A recognition also has dawned on me that the very structures that limit me are creating me, and pushing me to grow and develop in ways I wouldn't have otherwise. Working on holding both of these perspectives as true is one of the core sources of inspiration for my art.</p>
    <h3>Works:</h3>
    <p>In my piece <span class="underline">99</span>, presented at ADF I created a model using a <a href="https://github.com/ibab/tensorflow-wavenet/" alt="Tensorflow Wavenet Github Repo">TensorFlow implementation of DeepMind's WaveNet paper</a>. I recorded myself reading passages from Virginia Wolf's <span class="underline">To The Lighthouse</span> and trained a model using a GPU EC2 instance on AWS. I trained the model for 99,999 iterations over the course of a week. I generated audio samples at different stages and used these audio samples to generate the final piece of music for the piece. The piece is a quartet, where each of the dancers/neurons takes on movement that I generated and interprets it at different stages, mapped onto a diagonal. The piece traces the non-linear nature of a machine learning model's training. Some checkpoints produce clearer vocalizations than others, seemingly "regressing" in the process, but those diversions are crucial pieces of the learning process..</p>
    <p>In <span class="underline">The Other Being</span> I built a "dance spider" using an arduino and four infrared sensors. I plugged it into Ableton Live and created a piece of music that could be modulated and controlled using my body's proximity to the spider's legs. The two dancers (Florencia DeBrun and Cristina Lisot) created a duet that negotiates two different cultures and worldviews, exploring proximity to the unknown.</p>
    <p>A broader interpretation of the structures and processes that fascinate me is <span class="underline">Sestina</span>. Devised in collaboration with Sam, sestina uses the European poetic form to generate a structure for both music and movement. The sestina works by using six end-words and rearranging them in a specific pattern (algorithm?) to generate the order for that next stanza. Sam and I generated different 'moods' as each 'end-word' and switched between them according to the sestina's order. This piece brought up topics around the disconnection and disjointedness that can come from the rigid structures that shape our life.</p>
    <p>Finally, a piece currently in development is <span class="underline">ABAC</span> (working title). This piece draws from the ternary structure of the Sonata form in the classical period of music. At it's simplest it presents a theme (A) then a contrasting phrase (B) and then a recapitulation (A). The dancers side by side use gestures expressing anger, sensuality, concern, or sadness, growing each time further and further from the original gesture. tThe further from the origin the more chaotic the form, and the further away the dancers are. After reaching the depth of the recursive form, the dancers retrace their steps and come back to where they began. The music (also created by myself) follows this structure with a muted electronic beat that grows sharper as we work towards the middle of the form.</p>
  </div>
</div>

<style>
  .bio {
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    padding: 20px;
    overflow: scroll;
    flex: 1;
    width: 100%;
  }

  .content {
    position: absolute;
  }
</style>