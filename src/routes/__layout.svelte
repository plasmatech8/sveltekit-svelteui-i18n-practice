<script lang="ts">
	import '../app.css';
	import {
		AppShell,
		Navbar,
		Header,
		Burger,
		Button,
		SvelteUIProvider,
		Switch,
		Title
	} from '@svelteuidev/core';
	import { useViewportSize } from '@svelteuidev/composables';

	let opened = false;

	const links = [
		{ href: '/', name: 'Home' },
		{ href: '/buttons', name: 'Buttons' },
		{ href: '/modals', name: 'Modals' },
		{ href: '/typography', name: 'Typography' }
	];

	import { isDarkTheme } from '$lib/stores';

	const viewport = useViewportSize(); // TODO: breakpoint instead of viewport size
</script>

<SvelteUIProvider
	ssr
	withNormalizeCSS
	withGlobalStyles
	themeObserver={$isDarkTheme ? 'dark' : 'light'}
>
	<AppShell>
		<Header slot="header" override={{ p: '$smPX' }}>
			<div class="flex justify-between content-center">
				{#if $viewport.width < 993}
					<Burger {opened} on:click={() => (opened = !opened)} />
				{/if}
				<div class="flex-grow text-center">
					<div class="inline-block">
						<Title mt="xs" size="lg">My Test Application</Title>
					</div>
				</div>
				<Switch size="lg" offLabel="☀️" onLabel="🌙" bind:checked={$isDarkTheme} />
			</div>
		</Header>
		<Navbar slot="navbar" class="p-2" hidden={!opened} width={{ base: 300 }}>
			{#each links as link}
				<Button class="point" variant="subtle" href={link.href}>{link.name}</Button>
			{/each}
		</Navbar>
		<slot>This is the main content</slot>
	</AppShell>
</SvelteUIProvider>
