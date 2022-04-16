<template>
  <video
    :src="`https://${bucket}.s3.amazonaws.com/public/final.mov`"
    type='video/mp4'
    controls
  />
</template>

<script>
export default {
  name: 'WatchComponent',
  props: {
    msg: String
  },
  data() {
    return {
      bucket: process.env.VUE_APP_BUCKETEER_BUCKET_NAME,
    }
  },
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
