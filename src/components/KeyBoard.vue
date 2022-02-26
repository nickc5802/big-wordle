<template>
  <div class="keyboard">
   <table>
       <tr>
           <td @click="$emit('keyboard', 'KeyQ')">Q</td>
           <td @click="$emit('keyboard', 'Keyw')">W</td>
           <td @click="$emit('keyboard', 'KeyE')">E</td>
           <td @click="$emit('keyboard', 'KeyR')">R</td>
           <td @click="$emit('keyboard', 'KeyT')">T</td>
           <td @click="$emit('keyboard', 'KeyY')">Y</td>
           <td @click="$emit('keyboard', 'KeyU')">U</td>
           <td @click="$emit('keyboard', 'KeyI')">I</td>
           <td @click="$emit('keyboard', 'KeyO')">O</td>
           <td @click="$emit('keyboard', 'KeyP')">P</td>
       </tr>
       <tr>
           <td @click="$emit('keyboard', 'KeyA')">A</td>
           <td @click="$emit('keyboard', 'KeyS')">S</td>
           <td @click="$emit('keyboard', 'KeyD')">D</td>
           <td @click="$emit('keyboard', 'KeyF')">F</td>
           <td @click="$emit('keyboard', 'KeyG')">G</td>
           <td @click="$emit('keyboard', 'KeyH')">H</td>
           <td @click="$emit('keyboard', 'KeyJ')">J</td>
           <td @click="$emit('keyboard', 'KeyK')">K</td>
           <td @click="$emit('keyboard', 'KeyL')">L</td>
           <td @click="$emit('keyboard', 'Enter')" style="border-bottom: none;"></td>
       </tr>
       <tr>
           <td @click="$emit('keyboard', 'Backspace')">⌫</td>
           <td @click="$emit('keyboard', 'KeyZ')">Z</td>
           <td @click="$emit('keyboard', 'KeyX')">X</td>
           <td @click="$emit('keyboard', 'KeyC')">C</td>
           <td @click="$emit('keyboard', 'KeyV')">V</td>
           <td @click="$emit('keyboard', 'KeyB')">B</td>
           <td @click="$emit('keyboard', 'KeyN')">N</td>
           <td @click="$emit('keyboard', 'KeyM')">M</td>
           <td @click="$emit('keyboard', 'Enter')" style="border-right: none;"></td>
           <td @click="$emit('keyboard', 'Enter')" style="border-left: none; border-top: none;">⏎</td>
       </tr>
   </table>
  </div>
</template>

<script>
export default {
  name: 'KeyBoard'
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
</style>