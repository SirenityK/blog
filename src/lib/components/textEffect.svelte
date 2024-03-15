<script lang="ts">
	import { cn } from '$lib/utils.js';
	import type { Writable } from 'svelte/store';

	let className: any = undefined;
	export { className as class };
	export let text: string;
	export let delay: number = 100;
	export let fonts: string = 'Whisper, cursive';

	// @ts-ignore
	export let mountVar: Writable<boolean> | boolean = false;

	if (fonts === 'defaults') {
		delay = 5;
	}

	const handleEnd = (index: number) => {
		if (mountVar && index === text.length - 1) {
			// @ts-ignore
			mountVar.set(true);
		}
	};
</script>

<h1
	class={cn(
		'text-effect',
		fonts === 'defaults' ? 'text-xl' : 'max-md:text-5xl md:text-7xl',
		className
	)}
>
	{#each text as letter, index}
		{#if letter === ' '}
			&nbsp;
		{:else}
			<span
				style="animation-delay: {index * delay}ms;{fonts === 'defaults'
					? ''
					: `font-family: ${fonts}`}"
				on:animationend={() => handleEnd(index)}>{letter}</span
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
