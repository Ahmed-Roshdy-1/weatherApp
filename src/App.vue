<template>
  <div id="app" :class="(typeof weather.main != 'undefined' && weather.main.temp>16? 'warm':'')">
    <main>
      <input type="text" class="search-bar" placeholder="Search..." v-model="query" @keypress="fetchWeather" />
      
      <div class="weather-wrap" v-if="(typeof weather.main != 'undefined')">
        <div class="location-box">
          <div class="location">{{ weather.name }}, {{ weather.sys.country }}</div>
          <div class="date">{{ dateBuilder() }}</div>
        </div>
        <div class="weather-box">
          <div class="temp">{{weather.main.temp}}°C</div>
          <div class="weather">{{ weather.weather[0].main }}</div>
        </div>
      </div>
    </main>
  </div>
</template>

<script setup>
import { ref } from "vue";

const api_key = ref("0299cd4927503002496ec90ec3641bb6");
const url_base = ref("https://api.openweathermap.org/data/2.5/")
const query= ref("");
const weather=ref({})



function fetchWeather(e){
  // if(e.key == "Enter"){
    fetch(`${url_base.value}weather?q=${query.value}&units=metric&APPID=${api_key.value}`)
       .then(res=>{
         return res.json()
       }).then(setResults)

  // }
}

function setResults(results){
  weather.value=results;
  console.log(weather.value);

}

function dateBuilder(){
    let d= new Date();
    let months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
    let days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];

    let day=days[d.getDay()];
    let date=d.getDate();
    let month=months[d.getMonth()];
    let year = d.getFullYear();

    return `${day} ${date} ${month} ${year}`
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "montserrat", sans-serif;
  background: rgb(0, 0, 0);
  height: 100vh;
}
#app {
  background: url("./assets/cold-bg.jpg") no-repeat;
  background-size: cover;
  background-position: center;
  transition: 0.4s;
  height: 100vh;
}

#app.warm{
  background-image: url('./assets/warm-bg.jpg');
}
main {
   height: 100vh;
  /* min-height: 100vh; */
  padding: 3rem;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-direction: column;
  gap: 3rem;

  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.25), rgba(0, 0, 0, 0.75));
}
.search-box {
  width: 100%;
  margin-bottom: 30rem;
}

.search-bar {
  display: block;
  width: 100%;
  padding: 15px;

  color: #313131;
  font-size: 3vw;
  appearance: none;
  border: none;
  outline: none;
  background: none;
  box-shadow: 0 0 1rem rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0 2rem 0 2rem;
  transition: 0.4s;
}

.search-bar:focus {
  box-shadow: 0 0 2rem rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.75);
  border-radius: 2rem 0 2rem 0;
}
.location {
  color: #fff;
  font-size: 8vh;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}

.date {
  color: #fff;
  font-size: 3vh;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}

.weather-box {
  text-align: center;
  align-content: center;
}
.weather-box .temp {
  display: inline-block;
  padding: 10px 25px;
  color: #fff;
  font-size: 7vh;
  font-weight: 900;

  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.25);
  border-radius: 2rem;
  margin: 3rem 0;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

.weather-box .weather {
  color: #fff;
  font-size: 5vh;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

/* @media screen and (max-width: 1000) {
  .date {
  
     font-size: 0rem;
  
   }

   .weather-box .temp {
 
  font-size: 0.1rem;
 
}
  
} */
</style>
