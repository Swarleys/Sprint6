<script setup lang="ts">
import Scene from "./Scene.vue";
import  messages  from "../assets/data.json";
</script>

<template>
    <Scene :data="messages" />
</template>

<style scoped>
</style>