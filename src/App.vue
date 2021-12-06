<template>
  <div id="app">

    <h1>Would you rather?</h1>

  <would-you-rather 
    v-for="(question) in questions"
    v-bind:key="question.id" 
    v-bind:question="question.question"
    v-bind:answer1="question.question"
    v-bind:answer2="question.question"
    v-on:user-chose="userChose">
  </would-you-rather>
  
<h2 class=YouWouldRather>You would rather</h2>

<ul id="usersChoices">
<li v-for="(usersChoice) in usersChoices">
  {{ usersChoice }}
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
          question1: 'Would you rather be a robot or a cyborg?',
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
      userChose(usersChoice) {
        if (this.usersChoices.includes(usersChoice)) {
          return
          } else {
            this.usersChoices.push(usersChoice)
      }}}
    }

</script>






<style>

</style>