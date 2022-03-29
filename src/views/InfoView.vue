<template>
  <div class="home">
    <InfoComponent msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import InfoComponent from '@/components/InfoComponent.vue'

export default {
  name: 'InfoView',
  components: {
    InfoComponent
  }
}
</script>
