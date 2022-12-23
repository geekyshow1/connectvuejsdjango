<script setup>
import { onMounted } from "vue";
import useStudent from "../composables/studentApi";
const { studentData, error, getAllStudent } = useStudent();
onMounted(getAllStudent);
</script>

<template>
  <div>
    <h1>Connect Vue JS with Django</h1>
    <div v-if="error">Oops! Error encountered: {{ error.message }}</div>
    <div v-else-if="studentData">
      <div v-for="({ id, stuname, email }, i) in studentData" :key="id">
        <h2>
          {{ ++i }}
          {{ stuname }}
          {{ email }}
        </h2>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
