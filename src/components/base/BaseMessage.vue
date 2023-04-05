<script setup>
import { defineProps } from "vue";
defineProps({
  role: {
    type: String,
    required: false,
    default: "info",
  },
});
</script>

<template>
  <div>
    <p :class="role">
      <slot></slot>
    </p>
  </div>
</template>

<style scoped>
p {
  padding: 0.5 rem;
}

.info {
  background-color: #2196ff;
  color: #fff;
}

.warning {
  background-color: #ffc107;
  color: #fff;
}

.error {
  background-color: #f44336;
  color: #fff;
}
</style>
