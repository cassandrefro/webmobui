<script setup>
import { defineProps, defineEmits } from "vue";
defineProps({
  label: {
    type: String,
    default: "",
  },
  unit: {
    type: String,
    defalut: "",
  },
  modelValue: {
    type: Number,
    required: true,
  },
});

const emits = defineEmits(["update:modelValue"]);

function changeValue(event) {
  const value = event.target.value;
  console.log(value);
  emits("update:modelValue", Number(Number(value).toFixed(2)));
}
</script>

<template>
  <div>
    <label v-if="unit">{{ unit }}</label>
    <input
      type="number"
      :value="modelValue"
      :placeholder="label"
      @input="changeValue($event)"
    />
  </div>
</template>

<style scoped>
div {
  margin: 1 rem;
}

.label {
  margin-bottom: 0.5 rem;
  margin-right: 0.5 rem;
}

.input {
  padding: 0.5 rem;
}
</style>
