<template>
  <div class="paragraph">
    <div class="chartreuse">
      * Headphones or speakers are recommended to explore this project *
    </div>
  </div>

  <div class="paragraph">
    <video id="sampleMovie" width="640" height="360" preload controls>
      <source :src="`https://thresheld.s3.amazonaws.com/final.m4v`" />
      <source :src="`https://thresheld.s3.amazonaws.com/final.mp4`" />
      <source :src="`https://thresheld.s3.amazonaws.com/final.ogv`" />
      <source :src="`https://thresheld.s3.amazonaws.com/final.wemb`" />
      Your browser does not support the video tag.
    </video>
  </div>
</template>

<script>
  document.getElementById('app').style.background  = '#F3C5C5';
  document.getElementById('app').style.backgroundSize  = "cover";
  document.getElementById('app').style.color = "black";

  document.getElementById('nav-info').style.color = 'black';
  document.getElementById('nav-watch').style.color = 'black';
  document.getElementById('nav-explore').style.color = 'black';
  document.getElementById('nav-about').style.color = 'black';
  document.getElementById('nav-further').style.color = 'black';

  if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
    document.getElementById('app').style.height = "auto" ;
  } else {
    document.getElementById('app').style.height = "100vh"
  }

  export default {
    name: 'WatchComponent',
    props: {
      msg: String
    },
    data() {
      return {
        // bucket name
        bucket: process.env.VUE_APP_BUCKETEER_BUCKET_NAME,
      }
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  video {
    object-fit: cover;
    /* width: 100vw; */
    /* height: calc(100vh - 190px); */
    /* position: fixed ; */
    /* bottom: 0; */
    /* left: 0; */
    width: 100%;
    height: 60%;
  }

  .paragraph {
    margin-bottom: 32px;
  }
</style>
