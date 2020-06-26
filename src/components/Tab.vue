<template lang="html">
  <button v-bind:class="{'active': isActive}" @click="$emit('make-active', tabNum)">{{ sheetNumber + 0.1*tabNum || tabNum}}</button>
</template>

<script>
export default {
  name: "Tab",
  props: ["tabNum", "isActive", "sheetNumber"],
}
</script>

<style lang="css" scoped>
  button {
    padding: 10px;
    border: 0;
    background-color: white;
    width: 4rem;
  }

  button:hover {
    background-color: lightblue;
  }

  button:focus {
    outline: 0;
  }

  .active {
    background-color: lightgrey;
  }
</style>
