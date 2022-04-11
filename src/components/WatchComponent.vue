<template>
  <video
    src="https://<VUE_APP_BUCKETEER_BUCKET_NAME>.s3.amazonaws.com/public/main.mov"
    type="video/mov"
    controls
  />
</template>

<script>
console.log(process.env.VUE_APP_BUCKETEER_BUCKET_NAME);

export default {
  name: 'WatchComponent',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  video {
    object-fit: cover;
    width: 100vw;
    height: calc(100vh - 90px);
    position: fixed ;
    bottom: 0;
    left: 0;
  }
</style>
