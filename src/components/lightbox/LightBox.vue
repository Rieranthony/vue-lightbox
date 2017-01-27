<style src="./lightbox.scss" lang="scss"></style>

<template>
  <div class="lightbox" v-if="image" @click="close">
    <transition name="lightbox-fade">
      <lightbox-image :image="image" :key="image"></lightbox-image>
    </transition>
    <div class="lightbox__close" @click="close"></div>
    <div class="lightbox__btn lightbox__next" @click.stop.prevent="next"></div>
    <div class="lightbox__btn lightbox__prev" @click.stop.prevent="prev"></div>
  </div>
</template>

<script>
  import './LightBoxDirective'
  import LightboxImage from './LightboxImage'
  import store from './LightBoxStore'

  export default {
    components: { LightboxImage },
    data () {
      return {
        state: store.state
      }
    },
    methods: {
      close () { store.close() },
      prev () { store.prev() },
      next () { store.next() }
    },
    computed: {
      image () {
        if (this.state.index !== false) {
          return this.state.images[this.state.index]
        }
      }
    }
  }
</script>
