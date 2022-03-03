<script lang="ts">
	export let currentSentence: number;
</script>

<div class="flex gap-5 p-4 justify-around">
	<button
		type="button"
		class="text-4xl bg-slate-300 w-full py-4 border-2 border-black z-10"
		on:click={() => (currentSentence > 0 ? currentSentence-- : currentSentence)}>Anterior</button
	>
	<button
		type="button"
		class="text-4xl bg-slate-300 w-full py-4 border-2 border-black z-10"
		on:click={() => (currentSentence < 3 ? currentSentence++ : currentSentence)}>Següent</button
	>
</div>
