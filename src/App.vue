<template>
  <h1>Timer Project</h1>
  <button @click="startGame">Play</button>
  <blockVue v-if="isPlaying" />
</template>

<script>
import BlockVue from './components/BlockVue.vue'

export default {
  name: 'App',
  components: {BlockVue},
  data(){

    return{
        isPlaying:false,
        delay:0
    }
  },
  
  methods:{
    startGame(){
      this.delay = 2000 + Math.random()*5000
      this.isPlaying=true
      console.log(this.delay)

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
</style>
