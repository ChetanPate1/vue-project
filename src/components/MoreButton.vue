<template>
  <button class="more-button" type="button" name="more" :class="{ 'open' : open }">
    <span class="dripicons-plus"></span>
    <span class="behind">{{ behind }}</span>
  </button>
</template>

<script>
  import { objSize, timeNow } from '../HelperFunctions';

  export default {
    name: 'MoreButton',
    props: {
      open: Boolean,
      unWatched: Object,
      currentSeason: String
    },
    data() {
      return {
        behind: 0
      }
    },
    mounted() {
      this.behindCount(this.unWatched, this.currentSeason);
    },
    methods: {
      behindCount(seasons, currentSeason){
        let seasonsLimit = objSize(seasons) + currentSeason;
        let count = 0, j = 1, totalEpisodes = 0, season;

        for (currentSeason; currentSeason < seasonsLimit; currentSeason++) {
          season = seasons['season_' + currentSeason];
          totalEpisodes = objSize(season);
          for (j; j < totalEpisodes; j++) {
            if(!season[j].watched && season[j].airDate - timeNow() < 0){
              count++;
            }
          }
          j = 1;
        }

        let behindCount = (count > 0) ? '-'+ count : count;
        this.behind = behindCount;
      }
    }
  }
</script>
