<template>
  <div class="app-container">
    <BodyMassIndexForm @stats-entered="handleStatsEntered" />
    <div v-if="bmi" class="result-container">
      <h3>Your Body Mass Index (BMI) is:</h3>
      <p>{{ bmi }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import BodyMassIndexForm from './BodyMassIndexForm.vue';

const bmi = ref('');

function handleStatsEntered(data) {
  bmi.value = data.bmi;
}
</script>

<style>
.app-container {
  background-color: #e0e0e0;
  padding: 20px;
}

.result-container {
  margin-top: 20px;
  padding: 10px;
  background-color: #fff;
  border: 1px solid #ccc;
}
</style>
