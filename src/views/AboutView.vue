<template>
  <div class="about content">
    <AboutComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import AboutComponent from '@/components/AboutComponent.vue'

export default {
  name: 'AboutView',
  components: {
    AboutComponent
  }
}
</script>
