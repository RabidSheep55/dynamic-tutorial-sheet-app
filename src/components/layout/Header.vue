<template>
  <header>
    <p class="test">(Test using Vue.js)</p>
    <div class="title">
      <h1>Sheet {{sheetInfo.number}}: {{sheetInfo.name}}</h1>
      <p class="v">V{{sheetInfo.version}}</p>
    </div>
  </header>
</template>

<script>
  export  default {
    name: "Template",
    props: ["sheetInfo"]
  }
</script>

<style scoped>
  .test {
    text-align: center;
    font-size: 0.8rem;
  }

  .title {
    display: flex;
    flex-direction: row;
    align-items: center;
  }

  h1 {
    text-align: center;
    width: 100%;
  }

</style>
