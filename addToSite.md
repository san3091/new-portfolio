# Freelance projects for website

* Catalytic Quarterly 8, write up idea
* Catalytic Quarterly 9, collaborating with max
* Streaming site, what problems we're solving.
* 99 machine learning stuff


## Catalytic Sound Music Cooperative

### 8

I took over the online design for the Catalytic Quarterly for the 8th edition. At this time Federico, the designer in charge of the print version, had developed a concept for it that involved screenshots of the text and images taken from his desktop on TextEdit and Preview. He was interested in translating the digital-ness of the media onto print. The print version showed icons of .wav and .jpg files, creating what to me felt like a subtle parody of how we consume content online in a way that improvised music and free jazz often do.

In the interested of furthering this exploration I decided to recreate an apple gui in the browser, and use hyper-processed screenshots of the pdf proof for the print version as backgrounds. I began with the terminal—the application I spent the most time in—as the index. Then each link would open a "window" that could be closed. Hovering over the links changes the background image. I purposefully did not pre-load any assets to continue the spirit of opening up the medium we use to consume content.

This was my first attempt at integrating the philosophy and practice of free/experimental jazz with the development of a ui in a way that de-centralizes efficiency as the goal of user interaction, replacing it with the communication of an idea or feeling that a group of artists embody.

#### Blurb Version

Federico, the designer in charge of the print version, had developed a concept for it that involved screenshots of the text and images taken from his desktop on TextEdit and Preview. He was interested in translating the digital-ness of the media onto print. This was an attempt at integrating the philosophy and practice of free/experimental jazz with the development of a ui in a way that de-centralizes efficiency as the goal of user interaction, replacing it with the communication of an idea or feeling—in this case, pushing the boundaries between print and online media to the foreground.

### 9

For the 9th edition of the Catalytic Quarterly I brought in my dear friend and frontend artiste Max Oppenheimer. This edition would consist of only images, and we began building the online version as social distancing and quarantine regulations for COVID-19 started to be implemented. These images taken by touring artists and live performances felt like remnants of a world that was not accessible anymore. As a professional dancer I was feeling the deep void and disconnection from our art practice.

My vision for this project was to flip that discourse and instead focus on the ways that these images of the outside world and practicing artists document experiences that connect artists to one another. The images of concerts and strolls around the city you're touring in are immediately recognizable to practicing artists, and can be seen as the web that connects art-making in a society that is often very un-friendly to artists.

In an effort to be budget conscious, I brought in Max, who has an intuition in frontend work that is constantly surprising and inspiring. I knew he would be able to translate this vision into reality and teach me a couple things along the way. My role in this project became art-direction, project-manager, and DevOps, as well as a pair for Max to work through quick problem-solving.

The result is one of the more satisfying user experiences I've had the pleasure of building. I hope this ui sparked a sense of connectedness in the artists who submitted and the readers of the quarterly.

#### Blurb Version

My vision for this project was to flip that discourse of isolation during COVID-19 and instead focus on the ways that images of the outside world and touring artists document experiences that connect artists to one another. The images of concerts and strolls around the city you're touring in are immediately recognizable to practicing artists, and can be seen as the web that connects art-making in a society often very un-friendly to artists. I executed this vision in collaboration with my friend Max Oppenheimer, who has an intuition in frontend work that is constantly fresh and inspiring.
The result is one of the more satisfying user experiences I've had the pleasure of building. I hope this ui sparked a sense of connectedness in the artists who submitted and the readers of the quarterly.

### Streaming

Ken Vandermark, founder of Catalytic Sound, has a vision for artists to be compensated for their work that is so inspiring and honest. It comes from someone with decades of experience in the field. Hearing him speak of the pitfalls of music streaming platforms and distribution strategies that emphasize speed and efficiency over quality and fairness resonates deeply with me.

When Ken brought me on to build the Catalytic Quarterly he mentioned "a long-term dream" of a streaming platform for free jazz and improvised music that would compensate artists fairly and would facilitate the discovery of new projects as well as provide education on the history of the genre. A tall order. It was not my first priority at all—I had to build the online quarterly first, and also rehearse for tour with the dance company—but it wouldn't leave my mind as a radical idea, standing up to systems that take money from people who have the least of it and market them for profit.

After the cancellation of all performances and rehearsals due to COVID-19, seeing artists suffer economically all around me—and with Max by my side—I felt more motivated than ever to build the Catalytic Streaming site. We got to work, Max focused on creating an amazing ui while I took care of the third party integrations with Patreon and the backend built in Rails.

We are very close to having an MVP to start beta testing with members of the cooperative and I cannot wait for this to be live and to keep improving and growing the system to serve the community of artists who most need exposure and resources to sustain their practice.


#### Blurb Version

When Ken brought me on to build the Catalytic Quarterly he mentioned "a long-term dream" of a streaming platform for free jazz and improvised music that would compensate artists fairly and would facilitate the discovery of new projects as well as provide education on the history of the genre.
After the cancellation of all performances and rehearsals due to COVID-19, seeing artists suffer economically all around me—and with Max by my side—I felt more motivated than ever to build the Catalytic Streaming site. We got to work, Max focused on creating an amazing ui while I took care of the third party integrations with Patreon and the backend built in Rails.
We are very close to having an MVP to start beta testing with members of the cooperative and I cannot wait for this to be live and to keep improving and growing the system to serve the community of artists who most need exposure and resources to sustain their practice.

## 99

This is the nerdy tech part of 99, my machine learning/performance project

Summer 2019 I had six weeks away from my job as a web developer surrounded by dancers and musicians and a vibrant creative environment. Inspired by the work of <a href="https://twitter.com/quasimondo">Mario Klingemann</a> and <a href="https://twitter.com/glagolista">Helena Sarin</a> after seeing them speak at Eyeo Festival in Milwaukee, I decided to deep dive into machine learning as a medium for creative expression. The journey began with <a href="https://youtu.be/5v1JnYv_yWs">MIT 6.S191</a> and experimenting with the newly released public beta for <a href="https://runwayml.com/">Runway ML</a> and <a href="https://magenta.tensorflow.org/">Magenta</a>. Furious note-taking and tutorial watching led to the discovery of <a href="https://github.com/ibab/tensorflow-wavenet/">ibab/tensorflow-wavenet</a> and my decision to use ibab's work as my gateway into algorithmically generated sound.

I recorded ten minutes of myself singing only vowels in a fixed pentatonic scale. Then split that clip into roughly a hundred smaller clips and gleefully began the training and left the room to fix myself a congratulatory cup of tea. Minutes later my computer was the hottest it had ever been, <code>top</code> revealed <code>python3</code> pushing my cpu usage to a mindboggling 600%. I stopped the process and thought maybe I had a usable trained model after only fifteen minutes of pushing my macbook to the edge of its capacity. The checkpoint produced had only 27 steps and yielded only white noise when I generated one second (16000 samples) of audio.

Back to the drawing board. I needed more resources. I spun up a <code>t2.2xlarge</code> EC2 instance and requested access to a <code>p3.2xlarge</code> instance to use the <code>Deep Learning Ubuntu AMI</code>. It took the program 150 hours (6.25 days) to reach 21,800 steps and tensorboard was showing diminishing returns in terms of lowering loss. I stopped it and generated several short samples. For the first time I heard what sounded eerily similar in quality and tone to my voice glitched out and sung back at me in some variation of the scale I had used initially. This was when a friend suggested Ursula, the sexy octopus sea witch who collects voices, as the name for my cyborg friend.

At this point I got an email authorizing me to use a GPU <code>p3.2xlarge</code> instance!!

After my first pass I decided I wanted to train the next model using vowels <i>and</i> consonants, but still adhering to a scale. I read my favorite passage from Virginia Woolf's <i>To the Lighthouse</i> while singing in a set scale. I chopped this up into around 120 samples and spun up a <code>p3.2xlarge</code>, puzzled my way through setting up the AMI and starting the training process while monitoring the GPU with <code>nvidia-smi</code>. I had no idea what to expect and fixed myself dinner, checking in periodically. I was floored when 24 hours later, coming back exhausted from my last dance class of the day, I saw the model had reached 99,999 steps and stopped the training. I had set up a script that would download checkpoints along the way. I wanted to keep snapshots of the process so I could hear how the algorithm evolved. Here's the result:

Finally I generated some longer samples:

I pulled these samples into Ableton and started the next phase of composition, which eventually produced the full piece:


# Landing text

Queer dancer tech witch musician based in Chicago, IL.

I'm currently doing web development for [Catalytic Sound](https://catalyticsound.com/) and dance for [Lucky Plush Productions](https://www.luckyplush.com/). I love diagrams and structures and explore them through electronic music, machine learning, electronics, improvisation of all kinds, installation art, and all the intersections thereof.

Follow my work on on [instagram](https://www.instagram.com/santiago_mvmt/), and see some of my work on [vimeo](https://vimeo.com/santiagoqg).
