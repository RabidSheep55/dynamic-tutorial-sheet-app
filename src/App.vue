<template>
  <div id="app">
    <Header v-bind:sheetInfo="sheetInfo" />
    <div class="container">
      <Tabs :tabsInfo="tabsInfo" :sheetNumber="sheetInfo.number" v-bind:activeTab="activeTab" v-on:make-active="makeActive"/>
      <component v-bind:is="currentQuestion.type" v-bind:questionData="currentQuestion" :sheetNumber="sheetInfo.number"/>
    </div>
  </div>
</template>

<script>
// Import components
import Header from './components/layout/Header'
import Tabs from './components/Tabs'

import Field from './components/questions/Field'
import MCQ from './components/questions/MCQ'
import Section from './components/questions/Section'
import Show from './components/questions/Show'

// Import sheet data
import sheet from "./TutorialSheet.json"

// Package data for the Header component
const sheetInfo = {number: sheet.number, name: sheet.name, version: sheet.version};

// Get question numbers for Tabs component
const tabsInfo = sheet.questions.reduce((acc, q) => acc.concat(q.number), []);

// App starts with first question active
let activeTab = 1;
let currentQuestion = sheet.questions.find(q => q.number === activeTab);

export default {
  name: 'App',
  components: {
    Header,
    Tabs,
    Field,
    MCQ,
    Section,
    Show
  },
  data() {
    return {
      sheet,
      sheetInfo,
      tabsInfo,
      activeTab,
      currentQuestion
    }
  },
  methods: {
    makeActive(tabNum) {
      this.activeTab = tabNum;
      this.currentQuestion = sheet.questions.find(q => q.number === tabNum);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 40px;
}

.container {
  width: 80%;
  margin: auto;
}
</style>
