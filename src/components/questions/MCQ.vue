<template lang="html">
  <div class="question">
    <h2>{{ sheetNumber + 0.1*questionData.number || ''}} {{ questionData.name }}</h2>
    <p>{{ questionData.statement }}</p>
    <ul>
      <li v-bind:key="option.id" v-for="option in questionData.options">
        <input type="checkbox">
        <p class="option">{{ option }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "MCQ",
  props: ["questionData", "sheetNumber"]
}
</script>

<style lang="css" scoped>
  li {
    list-style-type: none;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-start;
  }

  .option {
    margin: 0;
    padding: 0.6rem;
  }
</style>
