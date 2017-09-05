<template>
  <div>
    <more-button @click.native="toggleOpen()" :open="open" :un-watched="seasons" :current-season="currentSeason"></more-button>
    <slide-out-panel :un-watched="seasons" :current-season="currentSeason" :open="open" ></slide-out-panel>
  </div>
</template>

<script>
  import MoreButton from './MoreButton';
  import SlideOutPanel from './SlideOutPanel';

  export default {
    name: 'MorePanel',
    props: {
      seasons: Object,
      currentSeason: String
    },
    data() {
      return {
        open: false
      }
    },
    methods: {
      toggleOpen(){
        this.open = !this.open;
      }
    },
    components: {
      MoreButton,
      SlideOutPanel
    }

  }
</script>
