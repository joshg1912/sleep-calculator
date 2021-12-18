<template>
  <div id="app">
    <div class="output">
    <form>
<h1>How many hours do you sleep per day?</h1>
     <p>Monday <input id="day1" type="text"></p>
     <p>Tuesday <input id="day2" type="text"></p>
     <p>Wednesday <input id="day3" type="text"></p>
      
      </form>
    <button v-on:click="myFunction()">Calculate!</button>
  </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  methods: {
    myFunction: function() {
      let day1 = document.getElementById('day1').value;
      let day2 = document.getElementById('day2').value;
      let day3 = document.getElementById('day3').value;
      const sum = parseFloat(day1) + parseFloat(day2) + parseFloat(day3);
      window.alert(sum);
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
