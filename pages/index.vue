<template>
  <div>
    <Hero />

    <AboutMe />

     <Testimonials />
  </div>
</template>

<script>
import Hero from '~/components/Hero.vue'
import AboutMe from '~/components/AboutMe.vue'
import Testimonials from '~/components/Testimonials.vue'

export default {
  layout: 'firstlayout', 

  components: {
    Hero,
    AboutMe,
    Testimonials, 
  },
}
</script>

<style scoped>

body {
  background-color: #ffffff;
}

.hero {
  background-color: #00796b; 
  color: white;
  padding: 60px;
  text-align: center;
}

.about-me {
  padding: 40px;
  background-color: #f4f7fc; 
}

.testimonials {
  padding: 40px 20px;
  background-color: #eeeeee; 
}

footer {
  background-color: #333;
  color: white;
  padding: 20px;
}
</style>
