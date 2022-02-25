<template>
  <div class="home">
    <input v-model="numGames">
    <button @click="$emit('play', numGames)">Play</button>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      numGames: 2
    }
  },
  emits: [
      'play'
  ]
}
</script>

<style scoped>
    
</style>
