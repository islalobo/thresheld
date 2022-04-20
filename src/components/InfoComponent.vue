<template>
  <div class="content-container">
    <div class="paragraph">
      Thresheld is a hybrid sound/video project that synthesizes personal experience, the study of seals and selkies in Celtic and Nordic folklore, and reverent imagination. 
    </div>

    <div class="paragraph">
      It explores how we might feel held by our ancestors in our own experiences of liminality and  endeavors to connect creatively to lineages from which we may have been disconnected. 
    </div>

    <div class="paragraph">
      Sourcing representations of queerness in nature and the folklore of the artists’ lineages emerged from a longing to connect with the queer and trans ancestors whose existence is often invisiblized.  Seals are liminal creatures, of both the land and sea, and selkies are shapeshifters. 
    </div>

    <div class="paragraph">
      This work is an experimental collaboration between these creatural thresholders, the artist, as a queer person of fluid gender and sexuality, and their child (N) who is amidst the shapeshifting experience of adolescence. It is a gesturing towards a sense of belonging in fluidity and an invitation to practice presence in the ever-shifting waters of time and change.
    </div>

    <div class="paragraph">
      <div class="chartreuse">
        * It is recommended that you use headphones or speakers to explore this project *
      </div>
    </div>
  </div>
</template>

<script>
  document.getElementById('app').style.background  = "url('../pinkwater.gif')";
  document.getElementById('app').style.backgroundSize  = "cover";
  navigator.userAgentData.mobile
    ? document.getElementById('app').style.height = "auto"
    : document.getElementById('app').style.height = "100vh" ;
  document.getElementById('app').style.color = "ghostwhite";

  export default {
    name: 'InfoComponent',
    data() {
      return {
        // bucket name
        bucket: process.env.VUE_APP_BUCKETEER_BUCKET_NAME,
      }
    },
    props: {
      msg: String
    }
  }
</script>
