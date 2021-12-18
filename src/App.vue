<template>
  <div id="app">
    <div class="sleephours">
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
    <button v-on:click="actualSleepHours()">Calculate!</button>
    <h2>How many hours would you like to sleep per day?</h2>
    <p>Ideally, i'd like to sleep <input id="idealhours" type="text"> hours a night</p><button v-on:click="idealSleepHours()">Enter</button>
    <p id="idealsleep"></p>
    <h3>So what's my outcome?</h3>
    <p id="sleepdebtresult"><button v-on:click="calculateSleepDebt()">Calculcate!</button></p>
  </div>
  </div>
</template>

<script>

//adds this variable so it can be accessed from within the methods 
let actualSleepHours = function actualSleepHours() {
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

// also adds this so it can be accessed within the methods
    let idealSleep = function idealSleepHours() {
      let idealHours = 8 * document.getElementById('idealhours').value;
      console.log(idealHours);
      document.getElementById("idealsleep").innerHTML = `Ideally you need to sleep ${idealHours} hours a week`;
    }
export default {
  name: 'App',
  methods: {

//keeps this here so it can perform the action on the html
    actualSleepHours: function () {
      let day1 = document.getElementById('day1').value;
      let day2 = document.getElementById('day2').value;
      let day3 = document.getElementById('day3').value;
      let day4 = document.getElementById('day4').value;
      let day5 = document.getElementById('day5').value;
      let day6 = document.getElementById('day6').value;
      let day7 = document.getElementById('day7').value;
      const sum = parseFloat(day1) + parseFloat(day2) + parseFloat(day3) + parseFloat(day4) + parseFloat(day5) + parseFloat(day6) + parseFloat(day7);
      document.getElementById("totalsleep").innerHTML = `You sleep ${sum} hours a week`;
    },


//keeps this here so it can perform action on html
    idealSleepHours: function() {
      let idealHours = 8 * document.getElementById('idealhours').value;
      console.log(idealHours);
      document.getElementById("idealsleep").innerHTML = `Ideally you need to sleep ${idealHours} hours a week`;
    },
    calculateSleepDebt: function() {
      if(actualSleepHours() === idealSleep()){
        document.getElementById("sleepdebtresult").innerHTML = 'Youre on track!'
      } else if (actualSleepHours() < idealSleep()) {
        document.getElementById("sleepdebtresult").innerHTML = 'Youre under sleeping!'
      }
      console.log(actualSleepHours)
      console.log(idealSleep)
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
