<script lang="ts">
	import { AppShell, Navbar, Header, Aside, Footer, ShellSection, Burger } from '@svelteuidev/core';
	let opened = false;
</script>

<AppShell>
	<Header slot="header" height={60} override={{ p: '$mdPX' }}>
		<Burger {opened} on:click={() => (opened = !opened)} />
		Head
	</Header>
	<Navbar slot="navbar" hidden={!opened} width={{ base: 300 }}>Nav</Navbar>
	<slot>This is the main content</slot>
</AppShell>
