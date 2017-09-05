<template>
  <div class="tab-panel" :class="{ 'active' : active }" ></div>
</template>

<script>
  export default {
    name: 'TabPanel',
    props: {
      active: Boolean,
      content: Array
    }
  }
</script>
