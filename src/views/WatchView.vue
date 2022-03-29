<template>
  <div class="watch">
    <WatchComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import WatchComponent from '@/components/WatchComponent.vue'

export default {
  name: 'WatchView',
  components: {
    WatchComponent
  }
}
</script>
