<script setup lang="ts">
import { Messages } from "../Interfaces/interfaces"
defineProps<{ data: Messages }>()
</script>

<template>
  <ul>
    <li v-for="message, index in data.messages" :key="index">{{ message }}</li>
  </ul>
</template>

<style scoped>
li {
  list-style: none;
}
</style>
