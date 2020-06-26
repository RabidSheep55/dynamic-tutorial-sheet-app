<template lang="html">
  <div class="tabs">
    <div v-bind:key="tabNum.id" v-for="tabNum in tabsInfo" >
      <Tab :tabNum="tabNum" :sheetNumber="sheetNumber" v-bind:isActive="activeTab === tabNum" v-on:make-active="$emit('make-active', tabNum)" />
    </div>
  </div>
</template>

<script>
import Tab from './Tab'

export default {
  name: "Tabs",
  components: {
    Tab
  },
  props: ["tabsInfo", "activeTab", "sheetNumber"]
}
</script>

<style lang="css" scoped>
  .tabs {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    flex-wrap: wrap;
  }
</style>
