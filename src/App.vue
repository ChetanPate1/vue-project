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

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
