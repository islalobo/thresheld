<template>
  <div class="explore content">
    <ExploreComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import ExploreComponent from '@/components/ExploreComponent.vue'

export default {
  name: 'ExploreView',
  components: {
    ExploreComponent
  }
}
</script>
