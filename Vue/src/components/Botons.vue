<script setup lang="ts">

const emits = defineEmits<{
    (e: 'nextScene'): void,
    (e: 'prevScene'): void,
}>();

const increase = () => {
    emits("nextScene",)
}
const decrease = () => {
    emits("prevScene")
}

</script>

<template>
    <div class="flex gap-5 p-4 justify-around z-10">
        <button
            type="button"
            class="text-4xl bg-slate-300 w-full py-4 border-2 border-black z-10 relative"
            @click="decrease"
        >Anterior</button>
        <button
            type="button"
            class="text-4xl bg-slate-300 w-full py-4 border-2 border-black z-10"
            @click="increase"
        >Següent</button>
    </div>
</template>

<style scoped>
</style> 