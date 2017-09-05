<template>
  <div class="slide-out-panel" :class="{ 'open' : open }" >

  </div>
</template>

<script>
  export default {
    name: 'SlideOutPanel',
    props: {
      open: Boolean
    }
  }
</script>
