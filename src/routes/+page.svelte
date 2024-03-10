<script lang="ts">
	const name = 'Dariel Fierro';
	const nlength = name.length;
	let count = 1;
	let displayName: string = '';

	const interval = setInterval(() => {
		displayName = name.slice(0, count);
		count++;
		if (count > nlength) {
			clearInterval(interval);
		}
	}, 100);
</script>

<main class="mt-5">
	<h1 class="text-2xl">{displayName}</h1>
</main>
