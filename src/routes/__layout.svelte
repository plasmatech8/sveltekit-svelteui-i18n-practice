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
		SvelteUIProvider
	} from '@svelteuidev/core';
	let opened = false;

	const links = [
		{ href: '/', name: 'Home' },
		{ href: '/foo', name: 'Foo' },
		{ href: '/bar', name: 'Bar' }
	];
</script>

<SvelteUIProvider ssr>
	<AppShell>
		<Header slot="header" height={60} override={{ p: '$mdPX' }}>
			<Burger {opened} on:click={() => (opened = !opened)} />
			Head
		</Header>
		<Navbar slot="navbar" hidden={!opened} width={{ base: 300 }}>
			{#each links as link}
				<Button class="point" variant="subtle" href={link.href}>{link.name}</Button>
			{/each}
		</Navbar>
		<slot>This is the main content</slot>
	</AppShell>
</SvelteUIProvider>
