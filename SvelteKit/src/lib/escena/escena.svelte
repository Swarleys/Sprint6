<script lang="ts">
	import type { Messages } from '../interfaces/interfaces';
	export let data: Messages, currentSentence: number;
	$: src = `${data.messages[currentSentence].img.src}`;
	$: alt = `${data.messages[currentSentence].img.alt}`;
</script>

<img {src} {alt} class="absolute top-0" />
<ul class="flex flex-col justify-center gap-6 mt-6">
	{#each data.messages as { txt }, index (index)}
		<li
			class="text-center bg-slate-50/75 border-2 py-4 mx-8 rounded-[50px] border-black z-10"
			class:active={index === currentSentence}
		>
			{txt}
		</li>
	{/each}
</ul>

<style>
	.active {
		@apply bg-red-300;
	}
</style>
