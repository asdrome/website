<script lang="ts">
	import Navigation from '$lib/Navigation/Navigation.svelte';
	import MaterialSymbolsMenuOpenRounded from '~icons/material-symbols/menu-open-rounded';
	import '../app.postcss';
	import { AppShell, AppBar, Avatar, LightSwitch } from '@skeletonlabs/skeleton';
	import { initializeStores, Drawer, getDrawerStore } from '@skeletonlabs/skeleton';

	initializeStores();

	const drawerStore = getDrawerStore();
	function drawerOpen(): void {
		drawerStore.open({});
	}
</script>

<Drawer position="top"><Navigation /></Drawer>
<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="pageHeader">
		<!-- App Bar -->
		<AppBar background="bg-transparent">
			<svelte:fragment slot="lead">
				<Avatar src="https://www.asdrome.com/LogoColor.svg" />
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://discord.gg/EXqV7W8MtY"
					target="_blank"
					rel="noreferrer"
				>
					Discord
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://twitter.com/SkeletonUI"
					target="_blank"
					rel="noreferrer"
				>
					Twitter
				</a>
				<a
					class="btn btn-sm variant-ghost-surface"
					href="https://github.com/skeletonlabs/skeleton"
					target="_blank"
					rel="noreferrer"
				>
					GitHub
				</a>
				<LightSwitch />
				<button
					type="button"
					class="btn-icon btn-icon-lg variant-ghost-surface my-4"
					on:click={drawerOpen}><MaterialSymbolsMenuOpenRounded /></button
				>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
