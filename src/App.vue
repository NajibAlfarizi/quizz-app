<script setup>
import { ref, watch } from "vue";
import srcQuiz from "./data/quizes.json";
import QuizCard from './components/QuizCard.vue'

const quizes = ref(srcQuiz);
const search = ref("");
watch(search, () => {
  quizes.value = srcQuiz.filter((quiz) => {
    return quiz.title.toLowerCase().includes(search.value.toLowerCase());
  });
});
</script>

<template>
  <main>
    <header>
      <h1 id="title">Quiz App</h1>
      <input
        v-model.trim="search"
        type="text"
        id="search-input"
        placeholder="search"
      />
    </header>

    <section id="quiz-container">
      <QuizCard v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
    </section>
  </main>
</template>

<style scoped>
main {
  font-family: "Poppins", sans-serif;
  max-width: 900px;
  margin: 0 auto;
  cursor: default;
}

header {
  margin-top: 30px;
  margin-bottom: 10px;
  display: flex;
  align-items: center;
}

#title {
  font-weight: bold;
  margin-right: 30px;
}

#search-input {
  padding: 5px 10px;
  border: none;
  background-color: #c9c9c9;
  border-radius: 4px;
  display: flex;
  align-items: center;
}

#quiz-container {
  display: flex;
  flex-wrap: wrap;
  margin-top: 20px;
}
</style>
