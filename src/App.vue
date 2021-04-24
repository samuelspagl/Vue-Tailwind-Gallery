<template>
  <div class="justify-center">
    <div>
      <h1 class="font-bold font-sans text-2xl">This is a Mock-up Gallery</h1>
      <p>The Images are all from unsplash ;)</p>
    </div>
    <div class="flex justify-center"><Gallery :images=imgs /></div>
  </div>
  
</template>

<script>
import Gallery from './components/gallery.vue'

export default {
  name: 'App',
  components: {
    Gallery
  },
  data: ()=>({
    imgs:[
      {id:0, src:[require("./assets/jonathan-petit-unsplash.jpg")]},
      {id:1, src:[require("./assets/kevin-mueller-unsplash.jpg")]},
      {id:2, src:[require("./assets/jonathan-petit-unsplash.jpg")]},
      {id:3, src:[require("./assets/ryunosuke-kikuno-unsplash.jpg")]},
      {id:4, src:[require("./assets/vincent-van-zalinge-unsplash.jpg")]},
      {id:5, src:[require("./assets/jonathan-petit-unsplash.jpg")]},
      {id:6, src:[require("./assets/vincent-van-zalinge-unsplash.jpg")]},
      {id:7, src:[require("./assets/ryunosuke-kikuno-unsplash.jpg")]},
      {id:8, src:[require("./assets/kevin-mueller-unsplash.jpg")]},
    ],
  })
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
