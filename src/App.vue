<template>
  <div id='app'>
    <div class="container">
      <watchlist-card :watchlist="watchlist"></watchlist-card>
    </div>
  </div>
</template>

<script>
  import WatchlistCard from './components/WatchlistCard';

  export default {
    name: 'app',
    computed: {
      watchlist() {
        return this.$store.state.watchlist
      }
    },
    components: {
      WatchlistCard
    }
  }
</script>

<style src='./assets/css/main.css'></style>
