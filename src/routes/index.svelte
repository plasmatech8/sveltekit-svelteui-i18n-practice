<script lang="ts">
	import { Button, Title, Anchor, Modal } from '@svelteuidev/core';

	let opened = false;
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <Anchor href="https://kit.svelte.dev">kit.svelte.dev</Anchor> to read the documentation</p>

<!-- Buttons -->
<div class="my-5">Buttons:</div>
<Button class="m-10" />
<Button class="m-10 animate-bounce bg-red-600" />

<!-- Text Content -->
<div class="my-5">Text Content:</div>
<p class="text-6xl mb-5">6xl Text</p>
<Title>This is a SvelteUI Title</Title>
<h1>This is a H1 Title</h1>

<!-- Modals -->
<div class="my-5">Modals:</div>
<Modal {opened} onClose={() => (opened = false)} title="Introduce yourself!">Hello World!!!</Modal>
<Button on:click={() => (opened = true)}>Open Modal</Button>
{opened}
