<template>
  <video id="sampleMovie" width="640" height="360" preload controls>
    <source :src="`https://${bucket}.s3.amazonaws.com/public/final.m4v`" />
    <source :src="`https://${bucket}.s3.amazonaws.com/public/final.mp4`" />
    <source :src="`https://${bucket}.s3.amazonaws.com/public/final.ogv`" />
    <source :src="`https://${bucket}.s3.amazonaws.com/public/final.wemb`" />
    Your browser does not support the video tag.
  </video>
</template>

<script>
  document.getElementById('app').style.background  = "black";
  document.getElementById('app').style.backgroundSize  = "cover";
  window.navigator.userAgentData.mobile
    ? document.getElementById('app').style.height = "auto"
    : document.getElementById('app').style.height = "100vh" ;
  document.getElementById('app').style.color = "ghostwhite";

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
    width: 75%;
    height: 60%;
  }
</style>
