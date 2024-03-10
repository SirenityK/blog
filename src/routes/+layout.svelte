<script>
	import '../app.pcss';
	import { ModeWatcher } from 'mode-watcher';
	import * as Menubar from '$lib/components/ui/menubar/index';
	import { toggleMode } from 'mode-watcher';
</script>

<ModeWatcher />
<header class="menubar sticky flex">
	<Menubar.Root class="md:ml-auto">
		<Menubar.Menu>
			<Menubar.Trigger>Github</Menubar.Trigger>
			<Menubar.Content>
				<Menubar.Item>Jason</Menubar.Item>
				<Menubar.Sub>
					<Menubar.SubTrigger>Boring Calculator (private)</Menubar.SubTrigger>
					<Menubar.SubContent>
						<Menubar.Item>Boring Calculator</Menubar.Item>
						<Menubar.Item>Android Port</Menubar.Item>
						<Menubar.Item>old calculator</Menubar.Item>
					</Menubar.SubContent>
				</Menubar.Sub>
				<Menubar.MenubarSeparator />
				<Menubar.Item>Trash-game</Menubar.Item>
			</Menubar.Content>
		</Menubar.Menu>
	</Menubar.Root>
	<div class="ml-auto grid">
		<button on:click={toggleMode}>Toggle theme</button>
	</div>
</header>
<slot />

<style lang="scss">
	:global(body) {
		@apply mx-5 mt-5;
	}
</style>
