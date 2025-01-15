<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { spotifySignIn, supabase } from '$lib/supabaseClient';
</script>

<svelte:head>
	<title>Music Wizard</title>
</svelte:head>

<div class="flex h-full flex-col items-center justify-center gap-2 bg-[url('/herobanner.svg')]">
	<div class="text-center drop-shadow-md">
		<h1 class="text-3xl font-bold">Uncover your music</h1>
		<p class="text-lg">Dive into what makes your music unique</p>
	</div>
	{#await supabase.auth.getSession() then session}
		{#if session}
			<Button>Go to Dashboard</Button>
		{:else}
			<Button onclick={async () => await spotifySignIn()}>Get Started</Button>
		{/if}
	{/await}
</div>
