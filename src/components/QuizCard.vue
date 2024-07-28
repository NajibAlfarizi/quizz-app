<script setup>
const { quiz } = defineProps(["quiz"]);

</script>

<template>
  <div class="card">
    <img
      :src="quiz.img"
      :alt="quiz.title"
    />
    <div class="card-body">
      <h2>{{ quiz.title }}</h2>
      <p>{{ quiz.questions.length }} Questions </p>
    </div>
  </div>
</template>

<style scoped>
.card {
  width: 270px;
  margin-right: 30px;
  margin-bottom: 30px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  border-radius: 5px;
  overflow: hidden;
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.card:hover {
  transform: scale(1.05);
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
  cursor: pointer;
  transition: 0.3s ease-in-out;
}

.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  margin: 0;
}

.card-body {
  padding: 0 15px;
}

.card-body h2 {
  margin-top: 0;
  font-weight: bold;
}
</style>
