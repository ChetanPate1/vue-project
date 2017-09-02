<template>
  <div id="app">
    <watchlist-card></watchlist-card>
  </div>
</template>

<script>
  import WatchlistCard from './components/WatchlistCard'

  export default {
    name: 'app',
    components: {
      WatchlistCard
    }
  }
</script>

<style src="./assets/css/main.css"></style>
