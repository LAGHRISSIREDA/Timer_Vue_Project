<template>
  <div class="game">
  <h1>Timer Project</h1>
  <button class="btn" @click="startGame" :disabled="isPlaying">Play</button>
 </div> 
  <blockVue v-if="isPlaying" :delay="delay" @end='endGame'/>
  <ResultsVue  v-if="showResult" :score="score"/>
  
</template>

<script>
import BlockVue from './components/BlockVue.vue'
import ResultsVue from './components/ResultsVue.vue'

export default {
  name: 'App',
  components: {BlockVue,ResultsVue},
  data(){

    return{
        isPlaying:false,
        delay:null,
        score : null,
        showResult :false
    }
  },
  
  methods:{
    startGame(){
      this.delay = 2000 + Math.random()*5000
      this.isPlaying=true
      this.showResult=false

    },
    endGame(reaction){
      this.score = reaction
      this.isPlaying=false
      this.showResult=true
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
  color: #444;
  margin-top: 60px;
}

.btn{
  box-shadow: 1px 1px 5px black;
}
</style>
