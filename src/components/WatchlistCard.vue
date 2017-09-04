<template>
  <div class="watchlist-card" :style="{ backgroundImage: 'url('+ imgSrc +')' }" >

    <h2>{{ title }}</h2>
    <h4>{{ subHeading }}</h4>
    <h5>On Season {{ on.season }} Episode {{ on.episode }}</h5>

    <h6>Next <small>Aired Episode</small></h6>
  </div>
</template>

<script>
  export default {
    name: 'WatchlistCard',
    props: {
      title: String,
      subHeading: String,
      on: Object,
      imgSrc: String
    }
  }
</script>
