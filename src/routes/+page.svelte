<script>
	import { onMount } from 'svelte';
	import '../app.css';
	let mobileView = false;
	const navItems = [
		{ label: 'logo', href: '#' },
		{ label: 'About', href: '#' },
		{ label: 'Projects', href: '#' },
		{ label: 'Repositories', href: '#' },
		{ label: 'toggletheme', href: '#' }
	];
	const mobileHandler = () => (mobileView = !mobileView);
	const queryHandler = (/** @type {{ matches: any; }} */ e) => {
		if (!e.matches) {
			mobileView = false;
		}
	};
	onMount(() => {
		const mediaListener = window.matchMedia('(max-width: 767px)');
		mediaListener.addListener(queryHandler);
	});
</script>

<slot />

<nav class="bg-background font-sans h-45">
	<div class="max-w-980 px-20 m-auto box-border flex items-center h-full">
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div on:click={mobileHandler} class="w-6 h-4 relative cursor-pointer">
			<div class="content-none absolute w-full h-0.5 bg-background transition-all duration-75 transform origin-center" />
		</div>
		<ul class={`navbar-list${mobileView ? ' mobile' : ''}`}>
			{#each navItems as item}
				<li>
					<a href={item.href}>{item.label}</a>
				</li>
			{/each}
		</ul>
	</div>
</nav>

<h1 class="text-red-900 text-3xl">Welcome to SvelteKit</h1>

<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to r ead the documentation</p>
