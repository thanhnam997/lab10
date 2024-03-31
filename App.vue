<script setup>
import { ref } from 'vue';
import WouldYouRather from './components/WouldYouRather.vue';

// Data for the question and two answers
const wyrQuestion = ref('Live in a house shaped like a triangle or a house shaped like a circle?');
const wyrAnswer1 = ref('Triangle house');
const wyrAnswer2 = ref('Circle house');

// Will store the user's selection, either 'Triangle house' or 'Circle house'
const userSelection = ref('');

function updateUserSelection(userChoice) {
  userSelection.value = `Thanks! You chose ${userChoice}`;
}
</script>

<template>
  <div id="app">
    <h1>Would You Rather...</h1>

    <WouldYouRather
      :question="wyrQuestion"
      :answer1="wyrAnswer1"
      :answer2="wyrAnswer2"
      @answer-selected="updateUserSelection">
    </WouldYouRather>

    {{ userSelection }}

  </div>
</template>

<style scoped>
#app {
  background-color: aqua;
}
</style>

