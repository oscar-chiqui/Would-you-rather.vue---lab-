<template>
<div id="app">
  <h1>Would you rather</h1>

  <would-you-rather 
    v-for="question in questions"
    v-bind:key="question.id"
    v-bind:question="question"
    v-on:answer-changed="answerChanged">
  </would-you-rather>

  <li v-for="choice in choicesMade">{{choice}}</li>
</div>

</template>
  
</script>

import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name:'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      questions: [
        {
          id:0,
          question: Would you rather travel to london or Tokyo?,
          answer1: 'London',
          answer2: ''
        }

      ]
    }
  }
}






<style>

@import url('https://fonts.googleapis.com/css2?family=New+Tegomin&display=swap');

body {
  background: black;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  background: green;
}
</style>
