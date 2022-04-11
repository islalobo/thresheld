<template>
  <div class="explore">
    <div class="play" @click="toggleAudio">Play</div>

    <div class="audio-item">
      <audio
        id="body-audio"
        preload="metadata"
        ref="audio"
        style="width:300px;"
        loop
      >
        <source
          src="https://<VUE_APP_BUCKETEER_BUCKET_NAME>.s3.amazonaws.com/public/body.wav"
          type="audio/mpeg"
        />
        Your browser does not support the audio element.
      </audio>

      <input
        id="body-volume"
        :name="input_name"
        class="volume-toggle"
        max="1000"
        min="0"
        type="range"
        v-model="value_model"
        @change="updateVolume()"
      />

      <div>
        <details close>
          <summary>
            Title
          </summary>
          <div>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit,
            sed do eiusmod tempor incididunt ut labore et dolore magna
            aliqua. Ut enim ad minim veniam, quis nostrud exercitation
            ullamco laboris nisi ut aliquip ex ea commodo consequat.
          </div>
        </details>
      </div> 
    </div>
  </div>
</template>

<script>
  export default {
    name: 'ExploreComponent',
    data() {
      return {
        input_name: 'audio',
        value_model: 500,
      }
    },
    methods: {
      toggleAudio() {
        const audio = this.$refs.audio;
        console.log(audio);
        if (audio.pause) {
          audio.play();
          this.isPlaying = true;
        } else {
          audio.pause();
          this.isPlaying = false;
        }
      },
      updateVolume() {
        const audio = this.$refs.audio;
        audio.volume = this.value_model / 1000;
      }
    },
    mounted() {
      // do something when the app mounts
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .explore {
    text-align: justify;
    margin: auto 400px;
    padding-top: 20px;
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
    height: 50px;
    -webkit-appearance: none;
    background: #F9F1F0;
    outline: none;
    overflow: hidden;
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
