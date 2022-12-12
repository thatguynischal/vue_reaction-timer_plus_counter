<template>
  <h1>How fast are your fingers?</h1>
  <button @click="start" :disabled="isPlaying">Lets Play</button>
</template>

<script>
export default {
    data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false
    }
  },
  methods: {
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      console.log(this.delay)
      this.showResults=false
    },
    endGame(reactionTime){
    this.score= reactionTime
    this.isPlaying= false
    this.showResults= true
  }
  }

}
</script>


<style>

</style>