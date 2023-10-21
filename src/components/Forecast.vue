<template>
<div>

  <div v-if="gettingLocation">
    <i>Getting your location...</i>
  </div>

  <div>
    <v-date-picker></v-date-picker>
  </div>

  <div v-if="location">
    <h4>Your location data is {{ location.coords.latitude }}, {{ location.coords.longitude}}</h4>
  </div>
</div>
</template>

<script>
import  axios from 'axios'
import {ref} from "vue";

// const location = ref({
//   coords: {
//     latitude: 0,
//     longitude: 0
//   }
// })
const location = ref(null)
const gettingLocation = ref(false)
const errorStr = ref(null)
</script>

<script setup>

import {onMounted} from "vue";

async function getForecast() {

  axios.get('https://api.open-meteo.com/v1/forecast', {
    params: {
      latitude: 0,
      // longitude: location.coords.longitude.value
    }
  })
  .then(function (response) {
    return response
  })
  .catch(function (error) {
    console.log(error);
  })
  .finally(function () {
    // always executed
  });
}

function getLocation() {
  if(!("geolocation" in navigator)) {
      errorStr.value = 'Geolocation is not available.';
      return;
    }
    gettingLocation.value = true;
    navigator.geolocation.getCurrentPosition(pos => {
      gettingLocation.value = false;
      location.value = pos;
      console.log(pos)
    }, err => {
      gettingLocation.value = false;
      errorStr.value = err.message;
    })
}

onMounted(() => {
  getLocation()
  getForecast()
})
</script>
