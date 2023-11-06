<template>
  <div>
    <QuizHeader />
    <div>
      <Question :question="quiz.questions[currentQuestionIndex]" />
    </div>
  </div>
</template>

<script setup>
import Question from '../components/Question.vue'
import QuizHeader from '../components/QuizHeader.vue'
import quizzes from '../data/quizzes.json'
import { useRoute } from 'vue-router'
import { ref } from 'vue'

const route = useRoute()

const quizId = parseInt(route.params.id)

const quiz = quizzes.find((q) => q.id === quizId)

const currentQuestionIndex = ref(0)
</script>

<style scoped></style>
