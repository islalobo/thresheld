<template>
  <div class="further content">
    <FurtherComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import FurtherComponent from '@/components/FurtherComponent.vue'

export default {
  name: 'FurtherView',
  components: {
    FurtherComponent
  }
}
</script>
