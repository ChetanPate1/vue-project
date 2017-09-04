<template>
  <div class="frost-glass">
    <div class="frost" :style="{ backgroundImage: 'url('+ imgSrc +')' }" ></div>
  </div>
</template>

<script>
  export default {
    name: 'FrostGlass',
    props: {
      imgSrc: String
    }
  }
</script>
