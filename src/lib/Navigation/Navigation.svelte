<script lang="ts">
	import { getDrawerStore } from '@skeletonlabs/skeleton';
	import MaterialSymbolsTopPanelCloseOutline from '~icons/material-symbols/top-panel-close-outline';
	const drawerStore = getDrawerStore();

	function drawerClose(): void {
		drawerStore.close();
	}
</script>

<nav dir="rtl" class="list-nav p-2">
	<button type="button" class="btn-icon btn-icon-lg my-4" on:click={drawerClose}
		><MaterialSymbolsTopPanelCloseOutline /></button
	>

	<ul>
		<li><a href="/" on:click={drawerClose}>Homepage</a></li>
		<li><a href="/about" on:click={drawerClose}>About</a></li>
		<li><a href="/blog" on:click={drawerClose}>Blog</a></li>
		<li><a href="/contact" on:click={drawerClose}>Contact</a></li>
	</ul>
</nav>
