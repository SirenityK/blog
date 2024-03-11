<script lang="ts">
	import { onMount } from 'svelte';
	import { cn } from '$lib/utils.js';

	export let text: string;
	export let delay: number = 100;
	export let fonts: string = 'Whisper, cursive';
	export let className: string = '';
	let sizes = 'text-xl';
	if (fonts !== 'defaults') {
		sizes = 'max-md:text-6xl md:text-8xl';
	} else {
		delay = 5;
	}

	let nameSplits: string[] = [];

	onMount(() => {
		nameSplits = text.split('');
	});
</script>

<h1 class={cn('text-effect max-md:text-center', sizes, className)}>
	{#each nameSplits as letter, index}
		{#if letter === ' '}
			&nbsp;
		{:else}
			<span
				style="animation-delay: {index * delay}ms;{fonts === 'defaults'
					? ''
					: `font-family: ${fonts}`}">{letter}</span
			>
		{/if}
	{/each}
</h1>

<style lang="scss">
	@keyframes nameFading {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}
	.text-effect {
		span {
			display: inline-block;
			opacity: 0;
			animation: nameFading 500ms ease-in forwards;
		}
	}
</style>
