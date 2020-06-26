<template lang="html">
  <div class="question">
    <h2>{{ sheetNumber + 0.1*questionData.number || ''}} {{ questionData.name }}</h2>
    <p>{{ questionData.statement }}</p>
    <div class="answer">
      <input type="text" :placeholder="questionData.fieldText">
      <button type="button" name="button">Submit</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Field",
  props: ["questionData", "sheetNumber"]
}
</script>

<style lang="css" scoped>
  .answer {
    display: flex;
    flex-direction: row;
  }

  button {
    padding: 1rem;
    margin-left: 1rem;
    border: none;
  }

  button:hover {
    background-color: lightblue;
  }
</style>
