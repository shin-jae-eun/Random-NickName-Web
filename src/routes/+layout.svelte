<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import UserIcon from '$lib/assets/usericon.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<header class="header">
	<div class="circle-user-icon">
		<UserIcon width={25} height={25} />
	</div>
	<div class="header-text">
		<h1 class="header-title">Random Nickname Generator</h1>
	</div>
</header>

<main class="main-content">
	{@render children()}
</main>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: system-ui, -apple-system, sans-serif;
	}

	.header {
		display: flex;
		align-items: center;
		gap: 1rem;
		padding: 1rem 2rem;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
		position: sticky;
		top: 0;
		z-index: 100;
	}

	.circle-user-icon {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 35px;
		height: 35px;
		border-radius: 50%;
		background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
	}

	.header :global(svg) {
		flex-shrink: 0;
		filter: brightness(0) invert(1);
	}

	.header-text {
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
	}

	.header-title {
		margin: 0;
		font-size: 1.5rem;
		font-weight: 700;
		line-height: 1.2;
	}

	.main-content {
		padding: 2rem;
	}

	@media (max-width: 640px) {
		.header {
			padding: 0.75rem 1rem;
		}

		.header-title {
			font-size: 1.25rem;
		}

		.header-subtitle {
			font-size: 0.85rem;
		}
	}
</style>
