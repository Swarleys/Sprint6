<script setup lang="ts">
import { Messages } from "../Interfaces/interfaces"
import { computed, ref } from 'vue';
const { data, scene } = defineProps<{ data: Messages, scene: number }>();

let changeScene = ref(scene);

let src = computed(() => {
  changeScene.value = scene;

  return `${data.messages[changeScene.value].img.src}`
});
let alt = computed(() => {
  changeScene.value = scene;

  return `${data.messages[changeScene.value].img.alt}`
});
</script>

<template>
  <img :src="src" :alt="alt" />
  <ul class="flex flex-col justify-center gap-6 mt-6 z-10">
    <li
      v-for="message, index in data.messages"
      :key="index"
      class="text-center border-2 py-4 mx-8 rounded-[50px] border-black"
      :class="{ active: index === scene }"
    >{{ message.txt }}</li>
  </ul>
</template>

<style scoped>
.active {
  @apply bg-red-200;
}
</style>
