<template>
  <div class="keyboard">
   <table>
       <tr>
           <td>Q</td>
           <td>W</td>
           <td>E</td>
           <td>R</td>
           <td>T</td>
           <td>Y</td>
           <td>U</td>
           <td>I</td>
           <td>O</td>
           <td>P</td>
       </tr>
       <tr>
           <td>A</td>
           <td>S</td>
           <td>D</td>
           <td>F</td>
           <td>G</td>
           <td>H</td>
           <td>J</td>
           <td>K</td>
           <td>L</td>
           <td style="border-bottom: none;"></td>
       </tr>
       <tr>
           <td></td>
           <td>Z</td>
           <td>X</td>
           <td>C</td>
           <td>V</td>
           <td>B</td>
           <td>N</td>
           <td>M</td>
           <td style="border-right: none;"></td>
           <td style="border-left: none; border-top: none;"></td>
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