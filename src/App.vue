<template>
  <div id="app">
    <h1>Would you rather...</h1>
    <WouldYouRather v-bind:question="wyrQ"
      v-bind:answer1="wyrA1"
      v-bind:answer2="wyrA2"
      v-on:answer-changed="answerChanged">
    </WouldYouRather>

    <p>{{ user_ans }}</p>
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
      wyrQ:"Would you rather have toes for fingers or fingers for toes?",
      wyrA1: "Toes for fingers",
      wyrA2: "Fingers for toes",
      user_ans: ''
    }
  },
  methods: {
    answerChanged(choice) {
      this.user_ans=`Thanks! You chose ${choice} (you weirdo)`
    }
  }
}
</script>



<style>
body {
  background: navy;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: purple;
  margin-top: 60px;
  background: aquamarine
}
</style>
