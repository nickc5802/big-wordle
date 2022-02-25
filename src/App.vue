<template>
  <GamePage v-if="onGamePage"/>
  <HomePage v-else @play="() => onGamePage = true"/>
</template>

<script>
import GamePage from './pages/game.vue'
import HomePage from './pages/home.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    GamePage
  },
  data() {
    return {
      onGamePage: false
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
