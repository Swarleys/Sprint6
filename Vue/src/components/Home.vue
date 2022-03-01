<script setup lang="ts">
import Scene from "./Scene.vue";
import messages from "../assets/data.json";
import Botons from "./Botons.vue";
import { ref } from 'vue';
const currentSentence = ref(0);
const started = ref(false);

const increase = (): number => {
    if (currentSentence.value < 3) {
        currentSentence.value++;
    }
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
    <div v-if="!started" class="flex flex-col justify-center items-center gap-20 mt-20">
        <h1 class="text-6xl">Sprint6 Vue</h1>
        <p class="max-w-6xl text-center text-3xl">Aquest es el primer projecte que fem amb Vue al Sprint 6, es una historia interactiva que funciona fent click en un parell de butons que serveixen per avançar o retrocedir l'historia. Fes click en el següent boto quant estiguis preparat</p>
        <button type="button" @click="() => started = true" class="text-3xl p-4 bg-slate-300 rounded-lg border-2 border-slate-700">Comencem!</button>
    </div>
    <div v-if="started">
        <Botons @nextScene="increase()" @prevScene="decrease()" />
        <Scene :data="messages" :scene="currentSentence" />
    </div>
</template>

<style scoped>
</style>