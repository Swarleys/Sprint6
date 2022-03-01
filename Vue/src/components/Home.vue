<script setup lang="ts">
import Scene from "./Scene.vue";
import messages from "../assets/data.json";
import Botons from "./Botons.vue";
import { ref } from 'vue';
const currentSentence = ref(0);

const increase = (): number => {
    if (currentSentence.value < 3) {
        currentSentence.value++;
    }
    console.log(currentSentence.value);
    
    return currentSentence.value;
}
const decrease = (): number => {
    if (currentSentence.value > 0) {
        currentSentence.value--;
    }
    return currentSentence.value;
}

</script>

<template>
    <Botons @nextScene="increase()" @prevScene="decrease()" />
    <Scene :data="messages" :scene="currentSentence" />
</template>

<style scoped>
</style>