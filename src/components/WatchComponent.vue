<template>
  <video
    src="https://bucketeer-65e5a636-429d-49f8-ac47-fb62455857a6.s3.amazonaws.com/public/main.mov"
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
