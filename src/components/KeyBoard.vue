<template>
  <div class="keyboard">
   <table>
       <tr>
           <td :class="{'gray': guessedLetters.has('Q')}" @click="$emit('keyboard', 'KeyQ')">Q</td>
           <td :class="{'gray': guessedLetters.has('W')}" @click="$emit('keyboard', 'Keyw')">W</td>
           <td :class="{'gray': guessedLetters.has('E')}" @click="$emit('keyboard', 'KeyE')">E</td>
           <td :class="{'gray': guessedLetters.has('R')}" @click="$emit('keyboard', 'KeyR')">R</td>
           <td :class="{'gray': guessedLetters.has('T')}" @click="$emit('keyboard', 'KeyT')">T</td>
           <td :class="{'gray': guessedLetters.has('Y')}" @click="$emit('keyboard', 'KeyY')">Y</td>
           <td :class="{'gray': guessedLetters.has('U')}" @click="$emit('keyboard', 'KeyU')">U</td>
           <td :class="{'gray': guessedLetters.has('I')}" @click="$emit('keyboard', 'KeyI')">I</td>
           <td :class="{'gray': guessedLetters.has('O')}" @click="$emit('keyboard', 'KeyO')">O</td>
           <td :class="{'gray': guessedLetters.has('P')}" @click="$emit('keyboard', 'KeyP')">P</td>
       </tr>
       <tr>
           <td :class="{'gray': guessedLetters.has('A')}" @click="$emit('keyboard', 'KeyA')">A</td>
           <td :class="{'gray': guessedLetters.has('S')}" @click="$emit('keyboard', 'KeyS')">S</td>
           <td :class="{'gray': guessedLetters.has('D')}" @click="$emit('keyboard', 'KeyD')">D</td>
           <td :class="{'gray': guessedLetters.has('F')}" @click="$emit('keyboard', 'KeyF')">F</td>
           <td :class="{'gray': guessedLetters.has('G')}" @click="$emit('keyboard', 'KeyG')">G</td>
           <td :class="{'gray': guessedLetters.has('H')}" @click="$emit('keyboard', 'KeyH')">H</td>
           <td :class="{'gray': guessedLetters.has('J')}" @click="$emit('keyboard', 'KeyJ')">J</td>
           <td :class="{'gray': guessedLetters.has('K')}" @click="$emit('keyboard', 'KeyK')">K</td>
           <td :class="{'gray': guessedLetters.has('L')}" @click="$emit('keyboard', 'KeyL')">L</td>
           <td @click="$emit('keyboard', 'Enter')" style="border-bottom: none;"></td>
       </tr>
       <tr>
           <td @click="$emit('keyboard', 'Backspace')">⌫</td>
           <td :class="{'gray': guessedLetters.has('Z')}" @click="$emit('keyboard', 'KeyZ')">Z</td>
           <td :class="{'gray': guessedLetters.has('X')}" @click="$emit('keyboard', 'KeyX')">X</td>
           <td :class="{'gray': guessedLetters.has('C')}" @click="$emit('keyboard', 'KeyC')">C</td>
           <td :class="{'gray': guessedLetters.has('V')}" @click="$emit('keyboard', 'KeyV')">V</td>
           <td :class="{'gray': guessedLetters.has('B')}" @click="$emit('keyboard', 'KeyB')">B</td>
           <td :class="{'gray': guessedLetters.has('N')}" @click="$emit('keyboard', 'KeyN')">N</td>
           <td :class="{'gray': guessedLetters.has('M')}" @click="$emit('keyboard', 'KeyM')">M</td>
           <td @click="$emit('keyboard', 'Enter')" style="border-right: none;"></td>
           <td @click="$emit('keyboard', 'Enter')" style="border-left: none; border-top: none;">⏎</td>
       </tr>
   </table>
  </div>
</template>

<script>
export default {
  name: 'KeyBoard',
  props: ['guessedLetters'],
  emits: ['keyboard']
}
</script>

<style scoped>
    .keyboard {
        background: black;
        width: 100%;
        flex-grow: 0;
    }
    table {
        margin: auto;
        width: 100%;
        max-width: 550px;
    }
    td {
      width: 50px;
      height: 50px;
      border: 1px white solid;
      color: white;
    }
    .gray {
      background: #787c7e;
    }
</style>