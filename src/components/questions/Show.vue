<template lang="html">
  <div class="question">
    <h2>{{ sheetNumber + 0.1*questionData.number || ''}} {{ questionData.name }}</h2>
    <p>{{ questionData.statement}}</p>
  </div>
</template>

<script>
export default {
  name: "Show",
  props: ["questionData", "sheetNumber"]
}
</script>

<style lang="css" scoped>
</style>
