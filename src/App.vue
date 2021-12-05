<template>
  <div id="app">

    <h1>Would you rather?</h1>

  <would-you-rather 
    v-for="(question) in questions"
    v-bind:key="question.id" 
    v-bind:question="question.question">
  </would-you-rather>

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
          }
        ]
      }
    }
}

</script>






<style>

</style>