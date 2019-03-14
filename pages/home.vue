<template>
  <div style="justify-content: center; align-items: center; display:flex; flex-direction: column; margin-top: 20px;">
    <input type="text" style="border: 1px solid black;" v-model="newfruit">
    <v-btn style="border: 1px solid black;" v-on:click="addFruit()">LISA</v-btn>
    <ul>
    </ul>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        newfruit: "",
        fruits: ['asd', 'ads', 'sad', 'sda', 'dsa', 'das']
      }
    },
      methods: {
        addFruit() {
          if(this.newfruit != ""){
          this.fruits.push(this.newfruit);
          this.newfruit = "";
          }
        }
    }
  }
</script>

<style>

  li:nth-child(3){color: #ff00f3;}
</style>
