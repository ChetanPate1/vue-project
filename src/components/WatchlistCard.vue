<template>
  <div class="watchlist-card" :style="{ backgroundImage: 'url('+ imgSrc +')' }" >

    <h2>{{ title }}</h2>
    <h4>{{ subHeading }}</h4>
    <h5>On Season {{ on.season }} Episode {{ on.episode }}</h5>

    <h6>Next <small>Aired Episode</small></h6>

    <frost-glass :imgSrc="imgSrc"></frost-glass>
  </div>
</template>

<script>
  import FrostGlass from './FrostGlass';

  export default {
    name: 'WatchlistCard',
    props: {
      title: String,
      subHeading: String,
      on: Object,
      imgSrc: String
    },
    components: {
      FrostGlass
    }
  }
</script>
