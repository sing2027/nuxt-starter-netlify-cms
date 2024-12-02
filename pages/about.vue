<template>
  <div>
  
    <AboutMe />
    <AboutTeam/>
  
  </div>
</template>

<script>

import AboutMe from '~/components/AboutMe.vue'
import AboutTeam from '~/components/AboutTeam.vue'

export default {
  layout: 'special-layout',

  components: {

    AboutMe,
    AboutTeam,
  },
}
</script>

<style scoped>
</style>
