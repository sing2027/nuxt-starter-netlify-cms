<template>
    <div>
    
      <Blog />
  
    
    </div>
  </template>
  
  <script>
  
  import Blog from '~/components/Blog.vue'
  
  export default {
    layout: 'special-layout', 

    components: {
  
        Blog,
    },
  }
  </script>
  
  <style scoped>
  </style>
  