<script lang="ts">
	import '../app.pcss';
	import { ModeWatcher } from 'mode-watcher';
	import * as Menubar from '$lib/components/ui/menubar/index';
	import { toggleMode } from 'mode-watcher';
	import Sun from 'lucide-svelte/icons/sun';
	import { Button } from '$lib/components/ui/button';
	import Moon from 'lucide-svelte/icons/moon';

	const gitref = (repo: string) => {
		return `https://github.com/SirenityK/${repo}`;
	};
</script>

<ModeWatcher />
<header class="menubar sticky flex">
	<Menubar.Root class="md:ml-auto">
		<Menubar.Menu>
			<Menubar.Trigger>Github</Menubar.Trigger>
			<Menubar.Content>
				<Menubar.Item href={gitref('jason-voice-ai')}>Jason</Menubar.Item>
				<Menubar.Sub>
					<Menubar.SubTrigger>Boring Calculator (private)</Menubar.SubTrigger>
					<Menubar.SubContent>
						<Menubar.Item href={gitref('boringcalculator')}>Boring Calculator</Menubar.Item>
						<Menubar.Item href={gitref('android-boring-calculator')}>Android Port</Menubar.Item>
						<Menubar.Item href={gitref('old-calculator')}>old calculator</Menubar.Item>
					</Menubar.SubContent>
				</Menubar.Sub>
				<Menubar.MenubarSeparator />
				<Menubar.Item href={gitref('trash-game')}>Trash game</Menubar.Item>
			</Menubar.Content>
		</Menubar.Menu>

		<Menubar.Menu>
			<Menubar.Trigger>Posts</Menubar.Trigger>
		</Menubar.Menu>

		<Menubar.Menu>
			<Menubar.Trigger>Curriculum</Menubar.Trigger>
		</Menubar.Menu>
	</Menubar.Root>
	<div class="ml-auto grid">
		<!-- <button on:click={toggleMode}>Toggle theme</button> -->
		<Button on:click={toggleMode} variant="outline" size="icon">
			<Sun
				class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
			/>
			<Moon
				class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
			/>
			<span class="sr-only">Toggle theme</span>
		</Button>
	</div>
</header>
<slot />

<style lang="scss">
	:global(h1 h2 p span) {
		font-family: 'Inter', sans-serif;
		font-optical-sizing: auto;
		font-style: normal;
		font-variation-settings: 'slnt' 0;
	}
	:global(body) {
		@apply mx-5 mt-5;
	}
</style>
