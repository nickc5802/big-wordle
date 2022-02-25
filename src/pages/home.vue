<template>
  <div class="home">
    <button @click="$emit('play', 2)">Play</button>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  emits: [
      'play'
  ]
}
</script>

<style scoped>
    
</style>
