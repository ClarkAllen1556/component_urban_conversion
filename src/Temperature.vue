<script setup>
import { ref } from 'vue';
import Input from './components/Input.vue';

const CONVERSION_MULTIPLIER = 1.8;
const DEG_OFFSET = 32;
const VALID_NUM_REGEX = /^-?\d+\.?\d*$/g;

const tempC = ref(null);
const tempF = ref(null);

const convertToCelsius = (inputF) => {
  tempF.value = inputF;

  if (!inputF || !inputF.match(VALID_NUM_REGEX)) {
    tempC.value = null;
  } else {
    tempC.value = ((inputF - DEG_OFFSET) / CONVERSION_MULTIPLIER).toFixed(2);
  }
};

const convertToFahrenheit = (inputC) => {
  tempC.value = inputC;

  if (!inputC || !inputC.match(VALID_NUM_REGEX)) {
    tempF.value = null;
  } else {
    tempF.value = (inputC * CONVERSION_MULTIPLIER + DEG_OFFSET).toFixed(2);
  }
};
</script>

<template>
  <div :class="['flex', 'flex-col', 'items-start']">
    <label> Celsius </label>
    <Input
      :value="tempC"
      @update="convertToFahrenheit"
      placeholder="Degrees Celsius"
    />
  </div>

  <div :class="['flex', 'flex-col', 'items-start']">
    <label> Fahrenheit </label>
    <Input
      :value="tempF"
      @update="convertToCelsius"
      placeholder="Degrees Fahrenheit"
    />
  </div>
</template>

<style lang="css"></style>
