<script lang="ts">
	import * as Card from '$lib/components/ui/card';
	import { cn } from '$lib/utils.js';
	export let title: string;

	let className: undefined | string = undefined;
	export { className as class };
</script>

<div class={cn('flex justify-center', className)}>
	<Card.Root class="w-1/3 max-md:w-full">
		<Card.Header>
			<Card.Title class="text-center">{title}</Card.Title>
		</Card.Header>
		<Card.Content class="flex flex-row gap-6 overflow-x-auto sm:justify-center">
			<slot />
		</Card.Content>
	</Card.Root>
</div>
