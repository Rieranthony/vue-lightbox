<template>
  <div id="app">
    <h1>LightBox component with vueJS 2 by Anthony Riera :)</h1>
    <h3><a href="https://github.com/Rieranthony/vue-lightbox">Git repository here</a></h3>
    <p>Just click for open it <br><small>Loading can be slow due to lorempicsum.com servers ...</small></p>

    <a :href="'http://lorempicsum.com/futurama/800/600/' + n" v-lightbox v-for="n in 9">
      <img :src="'http://lorempicsum.com/futurama/150/150/' + n">
    </a>
    <lightbox></lightbox>
  </div>
</template>

<script>
import lightbox from './components/lightbox/LightBox.vue'

export default {
  name: 'app',
  components: {
    lightbox
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
