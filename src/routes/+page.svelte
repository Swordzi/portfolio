

<script>
	import { Button } from '@svelteuidev/core';
	import '../app.css';
</script>

<slot />

<ul class="list-none m-0 p-0 overflow-hidden bg-background">
	<li class="float-left py-5 px-5">
		<Button class="bg-transparent">Hello</Button>
	</li>
	<li class="float-left bg-red-200 ">
	
	</li>
</ul>

<h1 class="text-red-900 text-3xl">Welcome to SvelteKit</h1>

<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to r ead the documentation</p>
