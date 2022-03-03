<script setup lang="ts">
import { Messages } from "../Interfaces/interfaces"
import { computed} from 'vue';
const props = defineProps<{ data: Messages, scene: number }>();

let src = computed(() => `${props.data.messages[props.scene].img.src}`);
let alt = computed(() => `${props.data.messages[props.scene].img.alt}`);
</script>

<template>
  <ul class="flex flex-col justify-center gap-6 mt-6">
    <li
      v-for="message, index in data.messages"
      :key="index"
      class="text-center bg-slate-50/75 border-2 py-4 mx-8 rounded-[50px] border-black z-10"
      :class="{ active: index === scene }"
    >{{ message.txt }}</li>
  </ul>
    <img :src="src" :alt="alt" class="absolute top-0" />
</template>

<style scoped>
.active {
  @apply bg-red-200;
}
</style>
