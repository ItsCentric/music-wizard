<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import '../app.css';
	let { children } = $props();
</script>

<div class="flex h-full flex-col">
	<nav class="container flex items-center justify-between bg-background py-2">
		<a href="/" class="flex items-center gap-1">
			<img src="/favicon.ico" alt="logo" class="h-12 w-12" />
			<p class="text-2xl">Music Wizard</p>
		</a>
		<div>
			<Button disabled>Login</Button>
		</div>
	</nav>
	<main class="flex-1">
		{@render children()}
	</main>
</div>
