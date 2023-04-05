<script setup>
import BaseMessage from "./base/BaseMessage.vue";
import BaseInput from "./base/BaseInput.vue";
import { computed, ref } from "vue";

const kelvin = ref(0);
const celcius = computed(()=> kelvin.value -273.15);


function changeKelvin(value) {
  kelvin.value = value;
}

//setTimeout(() => {
//kelvin.value = 100;
//}, 2000);
</script>

<template>
  <base-message role="error">Error: please try again later</base-message>
  <base-message role="warning">Application in maintenance ...</base-message>
  <base-input
    label="Kelvin"
    unit="K"
    v-model="kelvin"
    :modelValue="kelvin"
    @update:modelValue="changeKelvin($event)"
  />
  <base-input :modelValue="celcius" label="Celcius" />
  <p>Hello main page</p>
</template>

<style scoped></style>
