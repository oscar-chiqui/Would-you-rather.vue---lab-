<template>

<!-- A link from the resource website  -->
<div id="app">
  <p><a href="https://conversationstartersworld.com/would-you-rather-questions/would-you-rather-questions-for-kids/">Conversation Starters World !</a></p>
  <h1>Would you rather ? </h1>  

  <would-you-rather 
    v-for="question in questions"
    v-bind:key="question.id"
    v-bind:question="question"
    v-on:answer-changed="answerChanged">
  </would-you-rather>

<!-- li for choices  and message as results   -->
  <li 
  v-for="choice in choicesMade">{{choice}}

  <p><b>Thanks for participating, see you later !</b></p> 
  </li>   

</div>

</template>

<!-- Each Vue component in a dedicated file using the .vue extension - known as a Single-File Component -->

<script>

import WouldYouRather from './components/WouldYouRather.vue'   // Import the components from WouldYouRather.vue

export default {
  name:'App',
  components: {
    WouldYouRather
  },
  data() {
    return {
      questions: [      // Questions is the return and the id's for each Would you rather "question"
        {
          id:0,
          question: '....travel to london or Tokyo?',  // first question ( answers)
          answer1: 'London',
          answer2: 'Tokyo'

        },
        {
          id:1,
          question: '...be batman or Superman ?',  // Second Question
          answer1: 'Batman',
          answer2: 'Superman'
        },
        {
          id:2,
          question: '...control the fire or water ?', // Third question 
          answer1: 'the fire',
          answer2: 'water'
        }
      ],
      choices: []
    }
  },
  methods: {
    answerChanged(choice, id) {       
      this.choices[id] = choice
    }
  },
  computed: {                 // With computed method  I used to modify, manipulate, and display data within the  components in a readable     
    choicesMade() {
      let userChoices = []
      this.choices.forEach ( c => {   //  calculate and display values based on a value or set of values in the data model. (choicesMade)
        if (c) {
          userChoices.push(c)
        }
      })
      return userChoices      
    }
  }
}

</script>

<style>

/* Body background  */
body {
  background: black;
}
/* The entire app modification as needed  */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  background: black;
}

li {
  font-size: xx-large;
  color: yellow;
}
/* Google font import method url  */

@import url('https://fonts.googleapis.com/css2?family=New+Tegomin&display=swap');

</style>
