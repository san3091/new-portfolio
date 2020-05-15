<script>
  import Works from './components/Works.svelte'

  let uid = 1
  const tech = [
    {
      id: uid++,
      title: "CQ #8",
      description: "<p>I took over the online design for the Catalytic Quarterly for the 8th edition. At this time Federico, the designer in charge of the print version, had developed a concept for it that involved screenshots of the text and images taken from his desktop on TextEdit and Preview. He was interested in translating the digital-ness of the media onto print. The print version showed icons of .wav and .jpg files, creating what to me felt like a subtle parody of how we consume content online in a way that improvised music and free jazz often do.</p><p>In the interested of furthering this exploration I decided to recreate an apple gui in the browser, and use hyper-processed screenshots of the pdf proof for the print version as backgrounds. I began with the terminal—the application I spent the most time in—as the index. Then each link would open a 'window' that could be closed. Hovering over the links changes the background image. I purposefully did not pre-load any assets to continue the spirit of opening up the medium we use to consume content.</p><p>This was my first attempt at integrating the philosophy and practice of free/experimental jazz with the development of a ui in a way that de-centralizes efficiency as the goal of user interaction, replacing it with the communication of an idea or feeling that a group of artists embody.</p>",
      outLink: "https://catalyticsound.com/quarterly/8/index.html",
      media: "images/cq-8.png",
    },
    {
      id: uid++,
      title: "CQ #9",
      description: "<p>For the 9th edition of the Catalytic Quarterly I brought in my dear friend and frontend artiste Max Oppenheimer. This edition would consist of only images, and we began building the online version as social distancing and quarantine regulations for COVID-19 started to be implemented. These images taken by touring artists and live performances felt like remnants of a world that was not accessible anymore. As a professional dancer I was feeling the deep void and disconnection from our art practice.</p><p>My vision for this project was to flip that discourse and instead focus on the ways that these images of the outside world and practicing artists document experiences that connect artists to one another. The images of concerts and strolls around the city you're touring in are immediately recognizable to practicing artists, and can be seen as the web that connects art-making in a society that is often very un-friendly to artists.</p><p>In an effort to be budget conscious, I brought in Max, who has an intuition in frontend work that is constantly surprising and inspiring. I knew he would be able to translate this vision into reality and teach me a couple things along the way. My role in this project became art-direction, project-manager, and DevOps, as well as a pair for Max to work through quick problem-solving.</p><p>The result is one of the more satisfying user experiences I've had the pleasure of building. I hope this ui sparked a sense of connectedness in the artists who submitted and the readers of the quarterly.</p>",
      outLink: "https://catalyticsound.com/quarterly/9/index.html",
      media: {
        image: "images/cq-9.png",
      }
    },
    {
      id: uid++,
      title: "Catalytic Soundstream",
      description: "<p>Ken Vandermark, founder of Catalytic Sound, has a vision for artists to be compensated for their work that is so inspiring and honest. It comes from someone with decades of experience in the field. Hearing him speak of the pitfalls of music streaming platforms and distribution strategies that emphasize speed and efficiency over quality and fairness resonates deeply with me.</p><p>When Ken brought me on to build the Catalytic Quarterly he mentioned a long-term dream of a streaming platform for free jazz and improvised music that would compensate artists fairly and would facilitate the discovery of new projects as well as provide education on the history of the genre. A tall order. It was not my first priority at all—I had to build the online quarterly first, and also rehearse for tour with the dance company—but it wouldn't leave my mind as a radical idea, standing up to systems that take money from people who have the least of it and market them for profit.</p><p>After the cancellation of all performances and rehearsals due to COVID-19, seeing artists suffer economically all around me—and with Max by my side—I felt more motivated than ever to build the Catalytic Streaming site. We got to work, Max focused on creating an amazing ui while I took care of the third party integrations with Patreon and the backend built in Rails.</p><p>We are very close to having an MVP to start beta testing with members of the cooperative and I cannot wait for this to be live and to keep improving and growing the system to serve the community of artists who most need exposure and resources to sustain their practice.</p>",
      outLink: "https://catalyticsound.com/quarterly/9/index.html",
      media: {
        image: "images/cq-9.png",
      }
    },
  ]
</script>

<div class='tech'>
  <Works works={tech} />
</div>

<style>
  .tech {
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    padding: 20px;
    width: 100%;
    height: 100%;
    position: absolute;
  }
</style>
