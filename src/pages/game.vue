<template>
  <div class="game">
    <GameInstance v-for="n in numGames" :key="n" :word="words[n - 1]" :guesses="guesses" :current="current" :guess="guess" />
  </div>
</template>

<script>
import GameInstance from '../components/GameInstance.vue';
import constants from '../constants.js'

export default {
  name: 'GamePage',
  components: {
      GameInstance
  },
  data() {
    return {
      words: this.getWords(),
      guesses: this.getInitialGuesses(),
      current: "",
      guess: 0
    }
  },
  props: ['numGames'],
  created() {
    document.addEventListener('keydown', this.keyDown);
  },
  methods: {
    keyDown(e) {
      if (e.code.startsWith('Key') && this.current.length < 5) {
        this.current += e.code.charAt(3);
      } else if (e.code === "Backspace" && this.current.length > 0) {
        this.current = this.current.substring(0, this.current.length - 1);
      } else if (e.code === "Enter" && this.current.length === 5 && constants.allowed.has(this.current.toLowerCase())) {
        this.guesses[this.guess] = this.current;
        this.guess++;
        this.current = "";
      }
    },
    getInitialGuesses() {
      let guesses = [];
      for (let i = 0; i < this.numGames + 5; i++) {
        guesses.push("");
      }
      return guesses;
    },
    getWords() {
      let words = []
      for (let i = 0; i < this.numGames; i++) {
        words.push(constants.answers[Math.floor(Math.random() * constants.answers.length)]);
      }
      return words;
    }
  }
}
</script>

<style scoped>
  game {
    display: flex;
    flex-direction: row;
  }
</style>
