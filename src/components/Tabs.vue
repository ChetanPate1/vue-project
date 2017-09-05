<template>
  <div class="tabs">
    <tab-button v-for="season in seasons"
      :name="'S '+ season[0]"
      :active="isTabSelected(season[0])"
      @click.native="tabSelect(season[0])" >
    </tab-button>
  </div>

</template>

<script>
  import TabButton from './TabButton';

  export default {
    name: 'Tabs',
    props: {
      seasons: Object,
      currentTab: String
    },
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
      TabButton
    }
  }
</script>
