<template>
  <div class="explore">
    <div class="play" @click="toggleAudio">
      <div :text="text" class="controls">
        <strong>{{ text }}</strong>
      </div>
    </div>

    <div class="paragraph">
      <div class="chartreuse">
       * Headphones or speakers are reccommended to explore this project *
      </div>
    </div>

    <div class="audio-item">
      <audio
        id="body-audio"
        preload="metadata"
        ref="body-audio"
        style="width:300px;"
        loop
      >
        <source
          :src="`https://${bucket}.s3.amazonaws.com/public/body.wav`"
          type="audio/mpeg"
        />
        Your browser does not support the audio element.
      </audio>

      <input
        :id="body"
        class="volume-toggle"
        max="1000"
        min="0"
        type="range"
        @change="updateVolume"
      />

      <!-- <div> -->
        <details close>
          <summary :title="title">
            {{ audio[1].title }}
          </summary>
          <div>
            {{ audio[1].description }}
          </div>
        </details>
      <!-- </div>  -->
    </div>

    <div class="audio-item">
      <audio
        id="thrum-audio"
        preload="metadata"
        ref="thrum-audio"
        style="width:300px;"
        loop
      >
        <source
          :src="`https://${bucket}.s3.amazonaws.com/public/drone.wav`"
          type="audio/mpeg"
        />
        Your browser does not support the audio element.
      </audio>

      <input
        :id="thrum"
        class="volume-toggle"
        max="1000"
        min="0"
        type="range"
        @change="updateVolume"
      />

      <!-- <div> -->
        <details close>
          <summary :title="title">
            {{ audio[2].title }}
          </summary>
          <div>
            {{ audio[2].description }}
          </div>
        </details>
      <!-- </div>  -->
    </div>

    <div class="audio-item">
      <audio
        id="field-audio"
        preload="metadata"
        ref="field-audio"
        style="width:300px;"
        loop
      >
        <source
          :src="`https://${bucket}.s3.amazonaws.com/public/field.wav`"
          type="audio/mpeg"
        />
        Your browser does not support the audio element.
      </audio>

      <input
        :id="field"
        class="volume-toggle"
        max="1000"
        min="0"
        type="range"
        @change="updateVolume"
      />

      <!-- <div> -->
        <details close>
          <summary :title="title">
            {{ audio[3].title }}
          </summary>
          <div>
            {{ audio[3].description }}
          </div>
        </details>
      <!-- </div>  -->
    </div>

    <div class="audio-item">
      <audio
        id="song-audio"
        preload="metadata"
        ref="song-audio"
        style="width:300px;"
        loop
      >
        <source
          :src="`https://${bucket}.s3.amazonaws.com/public/vox.wav`"
          type="audio/mpeg"
        />
        Your browser does not support the audio element.
      </audio>

      <input
        :id="song"
        class="volume-toggle"
        max="1000"
        min="0"
        type="range"
        @change="updateVolume"
      />

      <!-- <div> -->
        <details close>
          <summary :title="title">
            {{ audio[4].title }}
          </summary>
          <div>
            {{ audio[4].description }}
          </div>
        </details>
      <!-- </div>  -->
    </div>
  </div>
</template>

<script>
  const bucket = process.env.VUE_APP_BUCKETEER_BUCKET_NAME;

  document.getElementById('app').style.background  = `url('https://${bucket}.s3.amazonaws.com/public/swirlclip2.gif')`;
  document.getElementById('app').style.backgroundSize  = "cover";

  if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
    document.getElementById('app').style.height = "auto"
  } else {
    document.getElementById('app').style.height = "auto"
  }

  export default {
    name: 'ExploreComponent',
    data() {
      return {
        // bucket name
        bucket: process.env.VUE_APP_BUCKETEER_BUCKET_NAME,
        // init play state text
        text: 'play all tracks',
        controls: {
          play: 'play all tracks',
          pause: 'pause all tracks',
        },
        audio: {
          // track titles
          3 : {
            id: 'field',
            title: 'Field',
            description: 'oceanic, pulse and shift of tide, field recordings from transitional seasons, queer times & spaces, intertidal zones, fall sleet on dried knotweed, underwater hydrophone recordings from seal sites, movement',
          },
          4: {
            id: 'song',
            title:  'Song',
            description: 'voice offerings, N’s songs for the seals & selkies, devotional, chorus of loved ones,  ode to gay seals, queer & trans ancestors, relationships through time, familial echos, reverberant hum, settling in uncertainty, thresholding',
          },
          1: {
            id: 'body',
            title: 'Body',
            description: 'seaweed on rocks, corporal rhythm, fog horns/bells, forms in motion, wayfinding, heartbeat and breath: “Before she goes underwater, the harbour seal will slow her heart.  Yes.  From 120 beats per minute to three or four heartbeats. Per minute. But first she exhales.  When she is underwater, the oxygen she needs is the oxygen she has.  Her blood breathes for her through her muscles as she descends as deep as 1,500 feet.  Deep enough for what she needs to do.  She slows her heart and listens, reaches, knows.  What if you could hear the world between your heartbeats? Slow down enough to deepen into trust?” from Undrowned: Black Feminist Lessons from Marine Mammals by Alexis Pauline Gumbs (p.142)',
          },
          2: {
            id: 'thrum',
            title: 'Thrum',
            description: 'deep, mercurial, analog bass pedals, N’s violin drone, processed electric guitar,  throbbing, ocean noise, water traffic, sustained, presence in fluidity, shapeshifting',
          }
        },
        // input ids
        body: 'body-volume',
        thrum: 'thrum-volume',
        field: 'field-volume',
        song: 'song-volume',
        // input init value
        value: 500,
      }
    },
    methods: {
      toggleAudio() {
        for (let index = 1; index <= Object.keys(this.audio).length; index++) {
          let audio = document.getElementById(`${this.audio[index].id}-audio`);
          if (audio.paused) {
            audio.play();
            this.text = this.controls.pause;
          } else if (!audio.paused) {
            audio.pause();
            this.text = this.controls.play;
          }
        }
      },
      updateVolume(event) {
        this.value = event.target.value;
        const id = event.target.id.replace('-volume', '');
        document.getElementById(`${id}-audio`).volume = this.value / 1000;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .controls {
    font-size: 0.875em;
  }

  .controls:hover {
    cursor: pointer;
  }

  /* Small devices (portrait tablets and large phones, 600px and up) */
  @media only screen and (min-width: 600px) {
    .explore {
      margin: auto 150px;
    }
  }

  /* Extra large devices (large laptops and desktops, 1200px and up) */
  @media only screen and (min-width: 1200px) {
    .explore {
      margin: auto 250px;
    }
  }

  .audio-item {
    min-height: 136px;
  }

  .audio {
    width: 100%;
    height: auto;
    margin: auto;  /* Magic! */
  }

  /* Small devices (portrait tablets and large phones, 600px and up) */
  @media only screen and (min-width: 600px) {
    .audio {
      width: 70%;
    }
  }

  /* Large devices (laptops/desktops, 992px and up) */
  @media only screen and (min-width: 992px) {
    .audio {
      width: 50%;
    }
  }

  .play {
    background: chartreuse;
    padding: 6px 0;
    width: 158px;
    color: black;
    border-radius: 100px;
    text-align: center;
  }

  input.volume-toggle {
    margin-top: 30px;
  }

  .disabled {
    background-color: black;
  }

  .volume-toggle {
    position: relative;
    top: 15px;
  }

  .volume-toggle {
    width: 100%;
    height: 40px;
    -webkit-appearance: none;
    background: #F9F1F0;
    outline: none;
    overflow: hidden;
    border-radius: 25px;
  }

  .volume-toggle::-webkit-slider-thumb {
    -webkit-appearance: none;
    width: 15px;
    height: 50px;
    background: #F3C5C5;
    cursor: pointer;
    border-left: 2px solid #F3C5C5;
    border-right: 2px solid #212529;
    box-shadow: -407px 0 0 400px #F3C5C5;
  }

  .description {
    margin: 20px 15px;
  }

  /* accordion */
  *:focus {
    outline: none;
  }

  div > details {
    position: relative;
    left: 16px;
    top: 16px;
  }

  details div {
    border-left: 2px solid #000;
    border-right: 2px solid #000;
    border-bottom: 2px solid #000;
    padding: 1.5em;
    color: black;
    background-color: #eee;
  }

  details div > * + * {
    margin-top: 1.5em;
  }

  details + details {
    margin-top: .5rem;
  }

  summary {
    list-style: none;
  }

  summary::-webkit-details-marker {
    display: none;
  }

  summary {
    /* border: 2px solid #000; */
    padding: .75em 1em;
    cursor: pointer;
    position: relative;
    padding-left: calc(1.75rem + .75rem + .75rem);
    color: ghostwhite;
    text-transform: uppercase;
  }

  summary:before {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: .75rem;
    content: "↓";
    width: 1.75rem;
    height: 1.75rem;
    background-color: #000;
    color: #FFF;
    display: inline-flex;
    justify-content: center;
    align-items: center;
    flex-shrink: 0;
  }

  details[open] summary:before {
    content: "↑";
  }

  .chartreuse {
    background: #F3C5C5;
    opacity: 0.678;
  }
</style>
