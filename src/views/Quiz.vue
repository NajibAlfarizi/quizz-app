<script setup>
import QuizHeader from "@/components/QuizHeader.vue";
import QuizContent from "@/components/QuizContent.vue";
import { useRoute } from "vue-router";
import quizes from "../data/quizes.json";
import { ref } from "vue";

const route = useRoute();

const quizId = parseInt(route.params.id);
const quiz = quizes.find((q) => q.id === quizId);

const curretQuestionIndex = ref(0);

</script>

<script setup></script>
<template>
  <QuizHeader />
  <QuizContent :question="quiz.questions[curretQuestionIndex]" />
</template>

<style scoped></style>
