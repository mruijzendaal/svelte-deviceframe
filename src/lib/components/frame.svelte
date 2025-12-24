<script lang="ts">
	import '$lib/assets/devices.min.css';
	import type { Snippet } from 'svelte';
	import Resizer from '$lib/components/resizer.svelte';
	import { cn } from '$lib/utils';

	type DeviceType =
		| 'phone-generic'
		| 'iphone-14'
		| 'iphone-14-pro'
		| 'iphone-x'
		| 'iphone-8'
		| 'the-iphone'
		| 'google-pixel-6-pro'
		| 'google-pixel-2-xl'
		| 'google-pixel'
		| 'galaxy-s8'
		| 'macbook-pro'
		| 'macbook-pro-2018'
		| 'macbook'
		| 'imac'
		| 'imac-pro'
		| 'surface-book'
		| 'surface-studio'
		| 'ipad-pro'
		| 'ipad-pro-2017'
		| 'surface-pro-2017'
		| 'apple-watch-ultra'
		| 'apple-watch-s8';

	type DeviceColor =
		| 'silver'
		| 'spacegray'
		| 'blue'
		| 'green'
		| 'pink'
		| 'red'
		| 'yellow'
		| 'orange'
		| 'purple'
		| 'gold'
		| 'rosegold'
		| 'black'
		| 'starlight';

	let {
		children,
		class: className = '',
		showHeader = false,
		showSensors = false,
		showButtons = true,
		showPower = true,
		showStripe = true,
		deviceType = 'phone-generic',
		deviceColor = 'green'
	}: {
		children?: Snippet;
		class?: string;
		showHeader?: boolean;
		showSensors?: boolean;
		showButtons?: boolean;
		showPower?: boolean;
		showStripe?: boolean;
		deviceType?: DeviceType;
		deviceColor?: DeviceColor;
	} = $props();
</script>

<Resizer class={cn('w-100', className)}>
	<div class="device device-{deviceType} device-{deviceColor}">
		<div class="device-frame">
			<div class="device-screen h-full w-full overflow-hidden">
				{#if children}
					{@render children()}
				{/if}
			</div>
		</div>
		{#if showHeader}
			<div class="device-header"></div>
		{/if}
		{#if showSensors}
			<div class="device-sensors"></div>
		{/if}
		{#if showButtons}
			<div class="device-btns"></div>
		{/if}
		{#if showPower}
			<div class="device-power"></div>
		{/if}
		{#if showStripe}
			<div class="device-stripe"></div>
		{/if}
	</div>
</Resizer>
