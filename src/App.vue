<template>
  <div id="app">
    <div class="output">
    <form>
<h1>How many hours do you sleep per day?</h1>
     <p>Monday <input id="day1" type="text"></p>
     <p>Tuesday <input id="day2" type="text"></p>
     <p>Wednesday <input id="day3" type="text"></p>
     <p>Thursday <input id="day4" type="text"></p>
     <p>Friday <input id="day5" type="text"></p>
     <p>Saturday <input id="day6" type="text"></p>
     <p>Sunday <input id="day7" type="text"></p>
     <p id="totalsleep"></p>
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
      let day4 = document.getElementById('day4').value;
      let day5 = document.getElementById('day5').value;
      let day6 = document.getElementById('day6').value;
      let day7 = document.getElementById('day7').value;
      const sum = parseFloat(day1) + parseFloat(day2) + parseFloat(day3) + parseFloat(day4) + parseFloat(day5) + parseFloat(day6) + parseFloat(day7);
      document.getElementById("totalsleep").innerHTML = `You sleep ${sum} hours a week`;
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
