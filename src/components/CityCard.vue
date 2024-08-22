<template>
    <div
      class="flex py-6 px-3 bg-weather-secondary rounded-md shadow-md cursor-pointer"
    >
      <div class="flex flex-col flex-1">
        <h2 class="text-3xl">{{ city.city }}</h2>
        <h3>{{ city.state }}</h3>
      </div>
  
      <div class="flex flex-col gap-2">
        <p class="text-3xl self-end">
            {{ Math.round((city.weather.main.temp - 32) * (5 / 9)) }}&deg;C/{{ Math.round(city.weather.main.temp) }}&deg;F
        </p>
        <div class="flex gap-2">
          <span class="text-xs text-red-300">
            {{ Math.round((city.weather.main.temp_max - 32) * (5 / 9)) }}&deg;C/{{ Math.round(city.weather.main.temp_max) }}&deg;F
          </span>
          <span class="text-xs text-blue-300">
            {{ Math.round((city.weather.main.temp_min - 32) * (5 / 9)) }}&deg;C/{{ Math.round(city.weather.main.temp_min) }}&deg;F
          </span>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    city: {
      type: Object,
      default: () => {},
    },
  });
  </script>