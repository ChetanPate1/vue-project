<template>
  <div class="watchlist-card" :style="{ backgroundImage: 'url('+ watchlist.imgsrc +')' }" >
    <h2>{{ watchlist.series }}</h2>
    <h4>{{ watchlist.subHeading }}</h4>
    <h5>On Season {{ watchlist.on.season }} Episode {{ watchlist.on.episode }}</h5>
    <h6>Next <small>Aired Episode</small></h6>

    <more-panel
      :seasons="watchlist.unwatched"
      :current-season="watchlist.on.season"
      :current-episode="watchlist.on.episode">
    </more-panel>
    <frost-glass :img-src="watchlist.imgsrc"></frost-glass>
  </div>
</template>

<script>
  import MorePanel from './MorePanel';
  import FrostGlass from './FrostGlass';

  export default {
    name: 'WatchlistCard',
    props: {
      watchlist: Object
    },
    components: {
      MorePanel,
      FrostGlass
    }
  }
</script>
