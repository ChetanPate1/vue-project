<template>
  <div>
    <div class="panel-row" v-for="(episode, index) in season" v-if="index > 0" :key="episode.number" :class="{ 'disabled' : !episode.watched }" >
      <div class="col-35">
        <span class="aired-by"><i class="dripicons-feed"></i> {{ aired(episode.airDate).by }}</span>
      </div>
      <div class="col-45">
        Episode {{ episode.number }}
      </div>
      <div class="col-20" @click="watched(index, episode.airDate)">
        <span class="dripicons-preview" :class="{ 'active' : episode.watched }" ></span>
      </div>
    </div>
  </div>

</template>

<script>
  import { timeNow } from '../HelperFunctions';

  export default {
    name: 'PanelRow',
    props: {
      season: Array,
      currentSeason: String,
      currentEpisode: Number
    },
    methods: {
      watched(key, airDate){
        const season = this.season;
        const currentEpisode = parseInt(this.currentEpisode, 0);
        let isCurrentSeason = this.currentSeason === season[0].toString();
        var valid = key === currentEpisode || key === (currentEpisode - 1);

        if(!isCurrentSeason){
          return;
          if(!this.aired(airDate).isAired || !valid){
            return;
          }
        }

        season[key].watched = !season[key].watched;
        this.season = season;
      },
      aired(date) {
        date = parseInt(date, 0);
        let delta = Math.abs((date - timeNow()))/1000;
        let isAired = date - timeNow() < 0;
        let aired = { isAired: isAired };

        if( isAired ){
          aired.by = `- ${ Math.ceil(delta / 86400) } days`;
          if(Math.ceil(delta / 86400) > 30){
            aired.by = 'aired';
          }
        }else {
          aired.by = 'not aired';
        }

        return aired;
      }
    }
  }
</script>
