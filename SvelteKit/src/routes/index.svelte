<script lang="ts">
	import Scene from '../lib/escena/escena.svelte';
	import Botons from '../lib/botons/botons.svelte';
	import data from '../lib/data/data.json';
	let started = false;
	let currentSentence = 0;
</script>

{#if !started}
	<div class="flex flex-col justify-center items-center gap-20 mt-20">
		<h1 class="text-6xl">Sprint6 Svelte Kit</h1>
		<p class="max-w-6xl text-center text-3xl">
			Aquest es el primer projecte que fem amb Svelte Kit al Sprint 6, es una historia interactiva que
			funciona fent click en un parell de butons que serveixen per avançar o retrocedir l'historia.
			Fes click en el següent boto quant estiguis preparat
		</p>
		<button
			type="button"
			on:click={() => started = !started}
			class="text-3xl p-4 bg-slate-300 rounded-lg border-2 border-slate-700">Comencem!</button
		>
	</div>
{:else}
	<div class="max-w-[960px] m-auto">
		<Botons bind:currentSentence/>
		<Scene {data} {currentSentence} />
	</div>
{/if}
