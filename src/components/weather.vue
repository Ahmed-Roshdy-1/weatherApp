<template>
  <div class="container p-0">
   <div class="d-flex">
     <div class="card main-div w-100">
      <div class="p-3">
        <h2 class="mb-1 day">Tuesday</h2>
        <p class="text-light date mb-0">date</p>
        <small>time</small>
        <h2 class="place">
          <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512">
            <!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
            <path
              d="M256 0c17.7 0 32 14.3 32 32V66.7C368.4 80.1 431.9 143.6 445.3 224H480c17.7 0 32 14.3 32 32s-14.3 32-32 32H445.3C431.9 368.4 368.4 431.9 288 445.3V480c0 17.7-14.3 32-32 32s-32-14.3-32-32V445.3C143.6 431.9 80.1 368.4 66.7 288H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H66.7C80.1 143.6 143.6 80.1 224 66.7V32c0-17.7 14.3-32 32-32zM128 256a128 128 0 1 0 256 0 128 128 0 1 0 -256 0zm128-80a80 80 0 1 1 0 160 80 80 0 1 1 0-160z"
            />
            Rio
            <small>Country</small>
          </svg>
          <!-- <i class="fa fa-location"></i> -->
        </h2>
        <div class="temp">
          <h1 class="weather-temp">19&deg;</h1>
          <h2 class="text-light">description</h2>
        </div>
      </div>
    </div>
    <div class="card card-2 w-100">
      <table class="m-4">
        <tbody>
          <tr>
            <th>Sea Level</th>
            <td>100</td>
          </tr>
          <tr>
            <th>Sea Level</th>
            <td>100</td>
          </tr>
          <tr>
            <th>Sea Level</th>
            <td>100</td>
          </tr>
        </tbody>
      </table>
      <DaysWeather />
      <div class="d-flex m-3 justify-content-center" id="div_Form">
        <form action="">
          <input type="button" value="Change Location" class="btn change_btn btn-primary" />
        </form>
      </div>
    </div>
   </div>
  </div>
</template>

<script setup>
import DaysWeather from "./DaysWeather.vue"
</script>

<style scoped>
.weather-temp {
  margin: 0;
  font-weight: 700;
  font-size: 4em;
}
h2.mb-1.day {
  font-size: 2rem;
  font-weight: 400;
}
.main-div {
  border-radius: 20px;
  color: #fff;
  background-image: url("https://images.unsplash.com/photo-1572376636973-049ac950cb53?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1645&q=80");
  background-size: cover;
  background-position: center;
  background-blend-mode: overlay;
  background-color: rgba(0, 0, 0, 0.5);
  background-repeat: no-repeat;
}
.temp {
  position: absolute;
  bottom: 0;
}
.main-div:hover {
  transform: scale(1.1);
  transition: transform 0.5s ease;
  z-index: 1;
}

.card-2 {
  background-color: #212730;
  border-radius: 20px;
}

.card-details {
  margin-left: 19px;
}

.h1_left {
  position: absolute;
  bottom: 25px;
  left: 16px;
  font-size: 3vw;
  line-height: 1.2;
}

.h3_left {
  position: absolute;
  bottom: 25px;
  left: 16px;
  font-size: 3vw;
  line-height: 0.5;
}

.h3_left small {
  font-size: 1rem;
}

table {
  position: relative;
  left: 15px;
  border-collapse: separate;
  border-spacing: 15px;
  width: 85%;
  text-align: left;
  max-width: 600px;
  margin: 0 auto;
}

th,
td {
  font-size: 18px;
  color: #fff;
}
td {
  text-align: right;
}
table,
tr:hover {
  color: red;
}

.change_btn {
  background-image: linear-gradient(to right, #6e6e6e, #f44f44);
  border: none;
  box-shadow: 0rem 0rem 0.6rem #f45044;
  transition: transform 0.3s ease;
}
.change_btn:hover {
  transform: scale(0.9);
}
</style>
