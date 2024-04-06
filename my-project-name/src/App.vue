<template>
  <div class="app-container">
    <h1>Body Mass Index Calculator</h1>
    <BodyMassIndexForm @stats-entered="handleStatsEntered" />
    <div v-if="bmi" class="result-container">
      <h3>Your Body Mass Index (BMI) is:</h3>
      <p>{{ bmi }}</p>
    </div>
  </div>
</template>

<script setup>
// App.vue
import { ref } from 'vue';
import BodyMassIndexForm from './components/BodyMassIndexForm.vue';  // Adjust the import path accordingly


const bmi = ref('');

function handleStatsEntered(data) {
  const { height, weight, bmi: calculatedBmi } = data;
  bmi.value = calculatedBmi;
  console.log(`Height: ${height}, Weight: ${weight}, BMI: ${calculatedBmi}`);
}
</script>

<style>
.app-container {
  background-color: #3daf1b;
  padding: 20px;
}

.result-container {
  margin-top: 20px;
  padding: 10px;
  background-color: #810909;
  border: 1px solid #280dd9;
}
</style>
