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

<header class="w-full">
	<div class="flex h-14 items-center px-12 py-8">
		<nav class="flex flex-col space-x-4 md:flex-row md:space-x-4 md:space-y-0">
			{#each featureLists as fList}
				<Button href={fList.relPath} class="mx-auto flex items-center justify-center">
					<fList.icon class="size-5" />
					<span class="bg-primary font-semibold text-white">
						{fList.label}
					</span>
				</Button>
			{/each}
		</nav>
	</div>
</header>
