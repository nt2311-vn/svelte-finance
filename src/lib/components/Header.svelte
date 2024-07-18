<script lang="ts">
	import { HomeIcon, StoreIcon, Receipt, Icon } from 'lucide-svelte';
	import type { ComponentType } from 'svelte';
	import { Button } from './ui/button';

	type Feature = {
		label: string;
		icon: ComponentType<Icon>;
		relPath: string;
	};

	const featureLists: Feature[] = [
		{ label: 'Home', icon: HomeIcon, relPath: '/' },
		{ label: 'Stock', icon: StoreIcon, relPath: '/stock' },
		{ label: 'Pricing', icon: Receipt, relPath: '/pricing' }
	];
</script>

<header
	class="w-full bg-opacity-60 bg-gradient-to-r from-indigo-800 via-blue-800 to-black backdrop-blur-lg backdrop-filter"
>
	<div class="flex h-14 items-center px-12 py-8">
		<nav class="flex space-x-4">
			{#each featureLists as fList}
				<Button variant="ghost" href={fList.relPath} class="flex items-center space-x-2 text-white">
					<fList.icon class="h-5 w-5" />
					<span class="font-semibold">
						{fList.label}
					</span>
				</Button>
			{/each}
		</nav>
	</div>
</header>
