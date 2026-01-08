<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<title>Meeran Hassan | Security Engineer</title>
	<meta name="description" content="Security Engineer & Penetration Tester specializing in web application security, post-quantum cryptography, and cloud security." />
</svelte:head>

<div class="min-h-screen bg-bg text-fg">
	{@render children()}
</div>
