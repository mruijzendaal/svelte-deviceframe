<script>
	import Frame from '$lib/components/frame.svelte';
</script>

<Frame deviceType="phone-generic" deviceColor="spacegray" class="m-10 mx-auto h-200 w-100">
	<!-- <div class="h-200 w-100 border-none bg-red-500!"></div> -->
	<iframe
		class="h-200 w-100 border-none"
		src="https://en.wikipedia.org/wiki/Main_Page"
		title="Device preview"
	></iframe>
</Frame>
