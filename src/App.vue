<template>
  <GamePage v-if="onGamePage" :numGames="numGames"/>
  <HomePage v-else @play="play"/>
</template>

<script>
import GamePage from './pages/Game.vue'
import HomePage from './pages/Home.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    GamePage
  },
  data() {
    return {
      onGamePage: false,
      numGames: 1
    }
  },
  methods: {
    play(numGames) {
      this.numGames = numGames;
      this.onGamePage = true;
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
