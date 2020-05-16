<script>
  import Works from './components/Works.svelte'

  let uid = 1
  const tech = [
    {
      id: uid++,
      title: "CQ #8",
      description: "<p>Federico, the designer in charge of the print version, had developed a concept for it that involved screenshots of the text and images taken from his desktop on TextEdit and Preview. He was interested in translating the digital-ness of the media onto print. This was an attempt at integrating the philosophy and practice of free/experimental jazz with the development of a ui in a way that de-centralizes efficiency as the goal of user interaction, replacing it with the communication of an idea or feeling—in this case, pushing the boundaries between print and online media to the foreground.</p>",
      outLink: "https://catalyticsound.com/quarterly/8/index.html",
      media: "images/cq-8.png",
    },
    {
      id: uid++,
      title: "CQ #9",
      description: "<p>My vision for this project was to flip that discourse of isolation during COVID-19 and instead focus on the ways that images of the outside world and touring artists document experiences that connect artists to one another. The images of concerts and strolls around the city you're touring in are immediately recognizable to practicing artists, and can be seen as the web that connects art-making in a society often very un-friendly to artists. I executed this vision in collaboration with my friend Max Oppenheimer, who has an intuition in frontend work that is constantly fresh and inspiring</p><p>The result is one of the more satisfying user experiences I've had the pleasure of building. I hope this ui sparked a sense of connectedness in the artists who submitted and the readers of the quarterly.</p>",
      outLink: "https://catalyticsound.com/quarterly/9/index.html",
      media: "images/cq-9.png"
    },
    {
      id: uid++,
      title: "Catalytic Soundstream",
      description: "<p>Ken Vandermark has had a long-term dream of a streaming platform for free jazz and improvised music that would compensate artists fairly and would facilitate the discovery of new projects as well as provide education on the history of the genre.</p><p>After the cancellation of all performances and rehearsals due to COVID-19, seeing artists suffer economically all around me—and with Max by my side—I felt more motivated than ever to build the Catalytic Soundstream. We got to work, Max focused on creating an amazing ui while I took care of the third party integrations with Patreon on the Rails backend and DevOps stuff.</p>",
      media: "images/catalytic-logo.png"
    },
  ]
</script>

<Works works={tech} />
