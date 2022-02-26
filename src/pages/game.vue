<template>
  <div class="game">
    <div class="jumpBar">
      <button v-for="n in numGames" :key="n" @click="scroll(n)" :class="getClass(n)">{{n}}</button>
    </div>
    <div class="instancesContainer">
      <div class="instances" id="instances">
        <GameInstance v-for="n in numGames" :gameNum="n" :key="n" :word="words[n - 1]" :guesses="guesses" :current="current" :guess="guess" />
      </div>
    </div>
    <KeyBoard :guessedLetters="guessedLetters" @keyboard="(key) => keyDown({code: key})"/>
  </div>
</template>

<script>
import GameInstance from '../components/GameInstance.vue';
import constants from '../constants.js';
import KeyBoard from '../components/KeyBoard.vue';

export default {
  name: 'GamePage',
  components: {
      GameInstance,
      KeyBoard
  },
  data() {
    return {
      words: this.getWords(),
      guesses: this.getInitialGuesses(),
      current: "",
      guess: 0,
      correct: new Set(),
      guessedLetters: new Set()
    }
  },
  props: ['numGames'],
  created() {
    document.addEventListener('keydown', this.keyDown);
  },
  methods: {
    scroll(n) {
      document.getElementById('game' + n).scrollIntoView();
    },
    keyDown(e) {
      if (e.code.startsWith('Key') && this.current.length < 5) {
        this.current += e.code.charAt(3);
      } else if (e.code === "Backspace" && this.current.length > 0) {
        this.current = this.current.substring(0, this.current.length - 1);
      } else if (e.code === "Enter" && this.current.length === 5 && constants.allowed.has(this.current.toLowerCase())) {
        this.guesses[this.guess] = this.current;
        this.guess++;
        let index = this.words.indexOf(this.current.toLowerCase());
        if (index !== -1) {
          this.correct.add(index + 1);
        }
        for (let i = 0; i < this.current.length; i++) {
          this.guessedLetters.add(this.current.charAt(i));
        }
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
    },
    getClass(n) {
      if (this.correct.has(n)) return "green";
    }
  }
}
</script>

<style scoped>
  .game {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }
  .instancesContainer {
    display: flex;
    flex-grow: 1;
    position: relative;
  }
  .instances {
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    overflow: auto;
  }
  .jumpBar {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    position: relative;
    top: 0px;
    background: black;
    width: 100%;
  }
  .jumpBar * {
    border: 1px solid black;
    text-decoration: none;
    color: black;
    background: white;
  }
  .green {
      background: #6aaa64;
      color: white;
    }
</style>
