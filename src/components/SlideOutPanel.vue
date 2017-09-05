<template>
  <div class="slide-out-panel" :class="{ 'open' : open }" >
    <tabs :seasons="unWatched" :current-tab="currentSeason" ></tabs>
  </div>
</template>

<script>
  import Tabs from './Tabs';

  export default {
    name: 'SlideOutPanel',
    props: {
      open: Boolean,
      unWatched: Object,
      currentSeason: String,
      currentEpisode: Number
    },
    components: {
      Tabs
    }
  }
</script>
