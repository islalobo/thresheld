<template>
  <div class="paragraph">
    <div class="chartreuse">
      * Headphones or speakers are reccommended to explore this project *
    </div>
  </div>

  <div class="paragraph">
    <video id="sampleMovie" width="640" height="360" preload controls>
      <source :src="`https://${bucket}.s3.amazonaws.com/public/final.m4v`" />
      <!-- <source :src="`https://${bucket}.s3.amazonaws.com/public/final.mp4`" /> -->
      <source :src="`https://${bucket}.s3.amazonaws.com/public/final.ogv`" />
      <source :src="`https://${bucket}.s3.amazonaws.com/public/final.wemb`" />
      Your browser does not support the video tag.
    </video>
  </div>

  <div class="paragraph">
    <i>Thresheld</i> is a hybrid sound/video project that synthesizes personal experience, the study of seals and
    selkies in Celtic and Nordic folklore, and reverent imagination. 
  </div>

  <div class="paragraph">
    It explores how we might feel held by our ancestors in our own experiences of liminality and  endeavors
    to connect creatively to lineages from which we may have been disconnected. 
  </div>

  <div class="paragraph">
    Sourcing representations of queerness in nature and the folklore of the artists’ lineages emerged from a
    longing to connect with the queer and trans ancestors whose existence is often invisiblized.  Seals are
    liminal creatures, of both the land and sea, and selkies are shapeshifters. 
  </div>

  <div class="paragraph">
    This work is an experimental collaboration between these creatural thresholders, the artist, as a queer
    person of fluid gender and sexuality, and their child (N) who is amidst the shapeshifting experience of
    adolescence. It is a gesturing towards a sense of belonging in fluidity and an invitation to practice presence
    in the ever-shifting waters of time and change.
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

  if ( !/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
    document.getElementById('app').style.height = "auto" ;
  } else {
    document.getElementById('app').style.height = "auto"
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
