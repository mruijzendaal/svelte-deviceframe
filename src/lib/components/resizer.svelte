<script lang="ts">
	import { cn } from '$lib/utils';
	import { type Snippet } from 'svelte';

	let { children, class: className }: { children: Snippet; class?: string } = $props();

	let childWidth = $state(0);
	let childHeight = $state(0);
	let rootWidthReal = $state(0);

	let aspect = $derived(childHeight / childWidth);
	let containerHeight = $derived(Math.round(rootWidthReal * aspect));
	let scale = $derived(rootWidthReal / childWidth);
</script>

<div
	bind:clientWidth={rootWidthReal}
	class={cn('relative overflow-visible', className)}
	style:height={`${containerHeight}px`}
>
	<div
		bind:clientWidth={childWidth}
		bind:clientHeight={childHeight}
		class="absolute top-0 left-0 inline-block origin-top-left"
		style:transform="scale({scale})"
	>
		{@render children()}
	</div>
</div>
