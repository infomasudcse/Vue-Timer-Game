<template>
  <h1>Reacton Timer Game</h1>
  <button @click="startGame" :disabled="isPlaying">Play</button>

  <Block v-if="isPlaying" :delay="delay"  @end="endGame"/>
  
  <Result v-if="showResult" :score="score"/>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: {
    Block, Result
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false,
    }
  },
  methods: {
    startGame(){
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
      this.showResult = false
    },
    endGame(reactionTime){
      this.score = reactionTime
      this.isPlaying = false
      this.showResult = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:crimson;
  margin-top: 60px;
}
</style>
