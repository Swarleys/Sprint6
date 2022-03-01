<script setup lang="ts">
import { Messages } from "../Interfaces/interfaces"
defineProps<{ data: Messages, scene: number }>()
</script>

<template>
  <ul class="flex flex-col justify-center gap-6 mt-6">
    <li
      v-for="message, index in data.messages"
      :key="index"
      class="text-center border-2 py-4 mx-8 rounded-[50px] border-black"
      :class="{ active: index === scene }"
    >{{ message }}</li>
  </ul>
</template>

<style scoped>
.active {
  @apply bg-red-200;
}
</style>
