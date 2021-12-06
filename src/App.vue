<template>
  <div id="app">

    <h1>Would you rather?</h1>

  <would-you-rather 
    v-for="(question) in questions"
    v-bind:key="question.id" 
    v-bind:question="question.question"
    v-bind:answer1="question.answer1"
    v-bind:answer2="question.answer2"
    v-on:user-chose="userChose">
  </would-you-rather>
  
<p id=YouWouldRather>You would rather</p>

<ul id="usersChoices">
<li v-for="(choice) in usersChoices">
  {{ choice }}
</li>
</ul>





</div>

</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
    },
    data() {
      return {
        questions: [
          {id: 0,
          question: 'Would you rather be a robot or a cyborg?',
          answer1: 'Robot',
          answer2: 'Cyborg',
          },
          {id: 1,
          question: 'Would you rather be rich and unknown or famous but not rich?',
          answer1: 'Rich and unknown',
          answer2: 'Famous but not rich',
          },
          {id: 2,
          question: 'Would you rather swim in Jell-O or swim in Nutella?',
          answer1: 'Jell-o',
          answer2: 'Nutella'
          }],

          usersChoices: []
      }
    },
    methods: {
      userChose(choice) {
        // if (this.usersChoices.includes(choice)) {
        //   return
        //   } else {
            this.usersChoices.push(choice)
      }}
    }

</script>






<style>

</style>