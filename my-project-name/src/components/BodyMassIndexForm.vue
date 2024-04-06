<template>
  <div class="form-container">
    <h2>Body Mass Index Calculator</h2>
    <form @submit.prevent="calculateBMI">
      <div>
        <label for="height">Height (m):</label>
        <input type="number" id="height" v-model="height" step="0.01" required>
      </div>
      <div>
        <label for="weight">Weight (kg):</label>
        <input type="number" id="weight" v-model="weight" step="0.01" required>
      </div>
      <button type="submit">Calculate</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const height = ref('');
const weight = ref('');

const calculateBMI = () => {
  if (!height.value || !weight.value) return;

  const bmi = (weight.value / (height.value * height.value)).toFixed(2);
  emit('stats-entered', { height: height.value, weight: weight.value, bmi });
};

</script>

<style scoped>
.form-container {
  margin: 20px;
}
</style>
