<script lang="ts">
	import '../app.css';
	import {
		AppShell,
		Navbar,
		Header,
		Aside,
		Footer,
		ShellSection,
		Burger,
		Button,
		SvelteUIProvider,
		Switch,
		Group,
		Space,
		Title
	} from '@svelteuidev/core';
	let opened = false;

	const links = [
		{ href: '/', name: 'Home' },
		{ href: '/buttons', name: 'Buttons' },
		{ href: '/modals', name: 'Modals' },
		{ href: '/typography', name: 'Typography' }
	];

	import { isDarkTheme } from '$lib/stores';
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
				<Burger {opened} on:click={() => (opened = !opened)} />
				<Title mt="xs" size="lg">My Test Application</Title>
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
