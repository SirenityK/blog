<script lang="ts">
	import Capabilities from '$lib/components/capabilities.svelte';
	import TextEffect from '$lib/components/textEffect.svelte';
	import type { Writable } from 'svelte/store';
	import { writable } from 'svelte/store';

	const nameLabel: Writable<boolean> = writable(false);

	let _nameFinished: boolean;
	$: _nameFinished = $nameLabel;
</script>

<svelte:head>
	<link
		rel="stylesheet"
		href="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/devicon.min.css"
	/>
</svelte:head>

<main class="mx-5 mb-5 grid gap-10">
	<div class="flex w-full justify-center max-md:flex-col">
		<div class="items-center self-center md:w-1/4">
			<enhanced:img src="./user.jpeg" alt="personImage" class="max-md:rounded-xl md:rounded-l-xl" />
		</div>
		<div>
			<TextEffect class="p-6 text-center font-medium" text="Dariel Fierro" mountVar={nameLabel} />
			{#if _nameFinished}
				<TextEffect class="text-center" fonts="defaults" text="Ingeniero de software" />
				<TextEffect class="text-center" fonts="defaults" text="Desarrollador web" />
			{/if}
		</div>
	</div>

	<Capabilities title="Lenguajes en los que programo">
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg"
			loading="lazy"
			alt="python"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg"
			loading="lazy"
			alt="typescript"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg"
			loading="lazy"
			alt="typescript"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/kotlin/kotlin-original.svg"
			loading="lazy"
			alt="kotlin"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg"
			loading="lazy"
			alt="java"
			width="64"
			height="64"
		/>
	</Capabilities>
	<Capabilities title="Frameworks web">
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg"
			loading="lazy"
			alt="react"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nextjs/nextjs-original.svg"
			loading="lazy"
			alt="nextjs"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/svelte/svelte-original.svg"
			loading="lazy"
			alt="svelte"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/solidjs/solidjs-original.svg"
			loading="lazy"
			alt="solidjs"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.svgporn.com/logos/preact.svg"
			loading="lazy"
			alt="preact"
			width="64"
			height="64"
		/>
		<img
			src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original.svg"
			loading="lazy"
			alt="fastapi"
			width="64"
			height="64"
		/>
	</Capabilities>
</main>
