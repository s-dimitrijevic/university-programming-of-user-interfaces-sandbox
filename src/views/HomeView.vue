<script setup lang="ts">

import {ref} from "vue";
import {QuestionService} from "@/services/question.service.ts";

const questions = ref<any[]>([])

QuestionService.getAll()
    .then(rsp=>questions.value = rsp.data)

</script>

<template>
  <ul>
    <li>ID - Pitanje</li>
    <li v-for="q in questions"
        :class="q.questionId % 2 === 0 ? 'yellow': ''">
        {{q.questionId}} - {{q.text}}</li>
  </ul>
  <pre>{{questions}}</pre>
</template>

<style>
.yellow{
  color: yellow;
}
</style>