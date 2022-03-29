<template>
  <video
    src="https://css-tricks-post-videos.s3.us-east-1.amazonaws.com/blurry-trees.mov"
    type="video/mov"
    controls
  />
</template>

<script>
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
