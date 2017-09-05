<template>
  <div>
    <div class="tabs">
      <tab-button v-for="season in seasons"
        :key="season[0]"
        :name="'S '+ season[0]"
        :active="isTabSelected(season[0])"
        @click.native="tabSelect(season[0])" >
      </tab-button>
    </div>

    <div class="tabs-panels">
      <tab-panel v-for="season in seasons"
        :key="season[0]"
        :content="season"
        :active="isTabSelected(season[0])" >
      </tab-panel>
    </div>
  </div>

</template>

<script>
  import TabButton from './TabButton';
  import TabPanel from './TabPanel';

  export default {
    name: 'Tabs',
    props: [ 'seasons', 'currentTab' ],
    data(){
      return {
        tabActive: '1'
      }
    },
    methods: {
      tabSelect(tabNumber) {
        this.tabActive = tabNumber;
      },
      isTabSelected(number) {
        return this.tabActive == number;
      }
    },
    components: {
      TabButton,
      TabPanel
    }
  }
</script>
