<template>
  <div id="wyr">
    <h2>Make your choice!</h2>
    <div id="question">{{ question }}</div>
    <div id="answers">
      <input type="radio" id="answer-1" v-model="choice" :value="answer1" @change="choiceMade">
      <label for="answer-1">{{ answer1 }}</label>

      <input type="radio" id="answer-2" v-model="choice" :value="answer2" @change="choiceMade">
      <label for="answer-2">{{ answer2 }}</label>
    </div>
  </div>
</template>

<script setup>
import { defineEmits, defineProps, ref } from 'vue';

const { question, answer1, answer2 } = defineProps({
  question: String,
  answer1: String,
  answer2: String
});

const emit = defineEmits(['answer-selected']);

const choice = ref('');

function choiceMade() {
  emit('answer-selected', choice.value);
}
</script>

<style scoped>
#wyr {
  background-color: hotpink;
  padding: 20px;
}

#answers {
  padding: 10px;
}
</style>
