<template>
  <div class="frost-glass">
    <countdown-timer :to="1531771200000"></countdown-timer>
    <div class="frost" :style="{ backgroundImage: 'url('+ imgSrc +')' }" ></div>
  </div>
</template>

<script>
  import CountdownTimer from './CountdownTimer';

  export default {
    name: 'FrostGlass',
    props: {
      imgSrc: String
    },
    components: { CountdownTimer }
  }
</script>
