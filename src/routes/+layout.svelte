<script lang='ts'>
	import '../theme.postcss';
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	import Navigation from '$lib/components/Navigation.svelte';
</script>

<!-- App Shell -->
<AppShell slotSidebarLeft="w-0 lg:w-52 bg-surface-800">
	<!-- sidebar left-->
	<svelte:fragment slot="sidebarLeft">
		<div class="p-8 pb-0 font-serif font-bold text-2xl">
			Quick Navigation
			<hr class="border-none h-1 bg-primary-500 ">
			<hr class="border-none h-1 bg-secondary-500">
		</div>
		<Navigation/>
	</svelte:fragment>
	<!-- Page header -->
	<!-- Page Route Content -->
	<slot />
</AppShell>
