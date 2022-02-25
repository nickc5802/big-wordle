<template>
  <div class="home">
    <button @click="$emit('play')">Play</button>
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
