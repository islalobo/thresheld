<template>
  <div class="explore">
    <div class="play" @click="toggleAudio">
      <div :text="text" class="controls">{{ controls.play }}</div>
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
            {{ audio_1.title }}
          </summary>
          <div>
            {{ audio_1.description }}
          </div>
        </details>
      <!-- </div>  -->
    </div>

    <div class="audio-item">
      <audio
        id="drone-audio"
        preload="metadata"
        ref="drone-audio"
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
        :id="drone"
        class="volume-toggle"
        max="1000"
        min="0"
        type="range"
        @change="updateVolume"
      />

      <!-- <div> -->
        <details close>
          <summary :title="title">
            {{ audio_2.title }}
          </summary>
          <div>
            {{ audio_2.description }}
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
            {{ audio_3.title }}
          </summary>
          <div>
            {{ audio_3.description }}
          </div>
        </details>
      <!-- </div>  -->
    </div>

    <div class="audio-item">
      <audio
        id="vox-audio"
        preload="metadata"
        ref="vox-audio"
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
        id="vox"
        class="volume-toggle"
        max="1000"
        min="0"
        type="range"
        @change="updateVolume"
      />

      <!-- <div> -->
        <details close>
          <summary :title="title">
            {{ audio_4.title }}
          </summary>
          <div>
            {{ audio_4.description }}
          </div>
        </details>
      <!-- </div>  -->
    </div>
  </div>
</template>

<script>
  export default {
    name: 'ExploreComponent',
    data() {
      return {
        // bucket name
        bucket: process.env.VUE_APP_BUCKETEER_BUCKET_NAME,
        // init play state text
        controls: {
          play: 'play all tracks',
          pause: 'pause all tracks',
        },
        // track titles
        audio_1: {
          title: 'Body',
          description: 'seaweed on rocks / corporal rhythm / forms in motion / gesturing into belonging / seal sounds / heartbeat and breath / “Before she goes underwater, the harbour seal will slow her heart.  Yes.  From 120 beats per minute to three or four heartbeats. Per minute. But first she exhales.  When she is underwater, the oxygen she needs is the oxygen she has.  Her blood breathes for her through her muscles as she descends as deep as 1,500 feet.  Deep enough for what she needs to do.  She slows her heart and listens, reaches, knows.  What if you could hear the world between your heartbeats? Slow down enough to deepen into trust?” from Undrowned: Black Feminist Lessons from Marine Mammals by Alexis Pauline Gumbs. (p.142)',
        },
        audio_2: {
          title: 'Thrum',
          description: 'mercurial / throbbing / analog bass pedals / N violin drone / electric guitar / ocean noise / water traffic / presence in fluidity / shapeshifting',
        },
        audio_3 : {
          title: 'Field',
          description: 'sounds of transitional seasons / queer times & spaces / fall sleet on dried knotweed / intertidal zones / underwater recordings from seal sites / pulse and shift of tide / movement / liminal / cyclical',
        },
        audio_4: {
          title:  'Song',
          description: 'voice offerings / adaptations of N’s songs for the seals & selkies / devotional / odes to lineage / queer & trans ancestors / gay seals / echos / relationships through time / familial / care / reverberant offerings / reciprocity / settling in uncertainty / thresholding',
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
        // audio.play() or audio.pause()
        // text ...controls.text
        const audio = this.$refs.audio;
        console.log(audio);
        if (audio.paused) {
          audio.play();
          this.text = 'pause';
        } else {
          audio.pause();
          this.text = 'play all tracks';
        }
      },
      updateVolume(event) {
        console.log(event.target.value);
        console.log(event.target.id);

        const audio = document.getElementById(`${event.target.id}-audio`);
        console.log(audio);
        audio.volume = this.value / 1000;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
    background: #edd4da;
    cursor: pointer;
    border-left: 2px solid #edd4da;
    border-right: 2px solid #212529;
    box-shadow: -407px 0 0 400px #edd4da;
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
    left: 2px;
    top: 20px;
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
    border: 2px solid #000;
    padding: .75em 1em;
    cursor: pointer;
    position: relative;
    padding-left: calc(1.75rem + .75rem + .75rem);
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
</style>
