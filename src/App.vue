<template>
  <div id="app">
    <h1>Sleep Calculator</h1>
    <div class="sleephours">
    <form>
<h2>How many hours do you sleep per day?</h2>
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
    <button v-on:click="calculateSleepDebt()">Calculcate!</button><p id="sleepdebtresult"></p>
  </div>
  </div>
</template>

<script>

//adds this so it can be accessed from within the methods 
  function actualSleepHours() {
      let day1 = document.getElementById('day1').value;
      let day2 = document.getElementById('day2').value;
      let day3 = document.getElementById('day3').value;
      let day4 = document.getElementById('day4').value;
      let day5 = document.getElementById('day5').value;
      let day6 = document.getElementById('day6').value;
      let day7 = document.getElementById('day7').value;
      const sum = parseFloat(day1) + parseFloat(day2) + parseFloat(day3) + parseFloat(day4) + parseFloat(day5) + parseFloat(day6) + parseFloat(day7);
      document.getElementById("totalsleep").innerHTML = `You sleep ${sum} hours a week`;
      return sum
    }


// also adds this so it can be accessed within the methods
     function idealSleepHours() {
      let idealHours = 7 * document.getElementById('idealhours').value;
     //console.log(idealHours);
      document.getElementById("idealsleep").innerHTML = `Ideally you need to sleep ${idealHours} hours a week`;
      return idealHours
    }

export default {
  name: 'App',
  message:'sleep calculator',
  methods: {

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
      //important to have this so it returns a value when called
      return sum
    },


    idealSleepHours: function() {
      let idealHours = 7 * document.getElementById('idealhours').value;
      //console.log(idealHours);
      document.getElementById("idealsleep").innerHTML = `Ideally you need to sleep ${idealHours} hours a week`;
      //important to have this so it returns a value when called
      return idealHours
    },



    calculateSleepDebt: function() {
    console.log('clicked');
    console.log(idealSleepHours());
    console.log(actualSleepHours());
   if(actualSleepHours() === idealSleepHours()){
     document.getElementById("sleepdebtresult").innerHTML = 'Youre on track!'
   }
   else if (actualSleepHours() < idealSleepHours()) {
     let difference = idealSleepHours() - actualSleepHours();
     document.getElementById("sleepdebtresult").innerHTML = `Youre under sleeping! Add ${difference} hours to your sleep schedule to get on track.`
   }
   else if (idealSleepHours() > actualSleepHours()) {
     let difference = idealSleepHours() - actualSleepHours();
     document.getElementById("sleepdebtresult").innerHTML = `Youre over sleeping by ${difference} hours!`
   }
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