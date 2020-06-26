<template lang="html">
  <div class="question">
    <h2>{{ sheetNumber + 0.1*questionData.number || ''}} {{ questionData.name }}</h2>
    <p>{{ questionData.statement }}</p>
    <ol>
      <li v-bind:key="part.id" v-for="part in questionData.sections">
        <p class="option">{{ part }}</p>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "Section",
  props: ["questionData", "sheetNumber"]
}
</script>

<style lang="css" scoped>
</style>
