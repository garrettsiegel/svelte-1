<script>
	import Nested from '../Nested.svelte';
	import Package from '../Package.svelte';

	const pkg = {
		name: 'svelte',
		version: '3.0.0',
		speed: 'blazing',
		website: 'https://svelte.dev'
	};
</script>

<Nested answer={42} />
<Nested />

<Package {...pkg} />

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
