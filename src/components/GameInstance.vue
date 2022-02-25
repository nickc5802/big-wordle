<template>
  <div class="gameInstance">
      <table>
          <tr v-for="w in guesses.length" :key="guesses[w - 1]">
              <td v-for="l in 5" :key="l" :class="showGuess(w - 1) ? getClass(w - 1, l - 1) : ''">
                <span v-if="w - 1 === guess && showGuess(w - 1)">{{ current.charAt(l - 1) }}</span>
                <span v-else-if="w - 1 < guess && showGuess(w - 1)">{{ guesses[w - 1].charAt(l - 1) }}</span>
              </td>
          </tr>
      </table>
  </div>
</template>

<script>
export default {
  name: 'gameInstance',
  props: ['word', 'guesses', 'current', 'guess'],
  data() {
    return {

    }
  },
  methods: {
    getClass(w, l) {
      if (this.guesses[w].length === 0) return;
      let letter = this.guesses[w][l];
      return letter === this.word[l].toUpperCase() ? "green" : this.word.toUpperCase().includes(letter) ? "yellow" : "gray";
    },
    showGuess(w) {
      let index = this.guesses.indexOf(this.word.toUpperCase());
      return index >= w || index === -1;
    }
  }
    
}
</script>

<style scoped>
    table, .gameInstance {
      display: inline-block;
    }
    .gameInstance {
      margin: 2px;
    }
    td {
      width: 50px;
      height: 50px;
      border: 1px black solid;
    }
    .green {
      background: #6aaa64;
      color: white;
    }
    .yellow {
      background: #c9b458;
      color: white;
    }
    .gray {
      background: #787c7e;
      color: white;
    }

</style>