<script setup>
import { defineProps } from "vue";
const { questionPage, barPrecentage } = defineProps([
  "questionPage",
  "barPrecentage",
]);
</script>

<template>
  <header>
    <h4>Questions {{ questionPage }}</h4>
    <div class="bar">
      <div class="completion" :style="{ width: barPrecentage }"></div>
    </div>
  </header>
</template>

<style scoped>
header {
  margin-top: 20px;
}
header h4 {
  font-size: 30px;
}
.bar {
  width: 100%;
  height: 50px;
  border: 3px solid #adf7b6;
}
.completion {
  height: 100%;
  width: 0%;
  max-width: 900px;
  background-color: #adf7b6;
}
</style>
