<template>
  <div class="watchlist-card" :style="{ backgroundImage: 'url('+ imgSrc +')' }" >
    <h2>{{ title }}</h2>
    <h4>{{ subHeading }}</h4>
    <h5>On Season {{ on.season }} Episode {{ on.episode }}</h5>
    <h6>Next <small>Aired Episode</small></h6>

    <more-panel
      :seasons="watchlist.unwatched"
      :current-season="on.season"
      :current-episode="on.episode">
    </more-panel>
    <frost-glass :img-src="imgSrc"></frost-glass>
  </div>
</template>

<script>
  import MorePanel from './MorePanel';
  import FrostGlass from './FrostGlass';

  export default {
    name: 'WatchlistCard',
    props: {
      title: String,
      subHeading: String,
      on: Object,
      imgSrc: String,
      watchlist: Object
    },
    components: {
      MorePanel,
      FrostGlass
    }
  }
</script>
