<script lang="ts">
	import Frame from '$lib/components/frame.svelte';
</script>

<div class="mx-auto w-min p-2">
	<Frame deviceType="phone-generic" deviceColor="spacegray" class="m-10 w-100">
		<iframe
			class="h-200 w-100 border-none"
			src="https://en.wikipedia.org/wiki/Main_Page"
			title="Device preview"
		></iframe>
	</Frame>
</div>
