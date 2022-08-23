<template>
<button @click="opt1">Speed Test</button>
<button @click='opt2'>Counter</button>
<div v-if="clickSpeed">
  <h1>How fast are you boi?</h1>
  <button @click="start" :disabled="isPlaying">Lets Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
  <Result v-if="showResults" :apple="score"/>
</div>
<div class="counter">
  <Counter v-if="counterApp"/>
</div>
  
</template>

<script>
import Block from "./components/Block.vue";
import Result from './components/Result.vue';
import Counter from "./components/Counter.vue";


export default {
  name: 'App',
  components: { Block, Result, Counter },
  data(){
    return{
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      clickSpeed:false,
      counterApp: false
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
  },
  opt1(){
    this.clickSpeed = !this.clickSpeed
  },
  opt2(){
    this.counterApp = !this.counterApp
  }
  },
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  background: #0faf87;
  color: wheat;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px
}
button[disabled]{
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
