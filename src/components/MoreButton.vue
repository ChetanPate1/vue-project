<template>
  <button class="more-button" type="button" name="more" @click="toggle()" :class="{ 'open' : open }">
    <span class="dripicons-plus"></span>
    <span class="behind">{{ behindCount }}</span>
  </button>
</template>

<script>
  export default {
    name: 'MoreButton',
    data() {
      return {
        open: false,
        behindCount: 0
      }
    },
    methods: {
      toggle() {
        this.open = !this.open;
      },
      behindCount(){
        
      }
    }
  }
</script>
