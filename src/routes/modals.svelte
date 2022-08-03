<script lang="ts">
	import { Button, Modal, Title } from '@svelteuidev/core';
	let opened = false;
</script>

<Title mb="lg">Modals</Title>

<Button on:click={() => (opened = true)}>Open Modal</Button>
<Modal {opened} on:close={() => (opened = false)} title="Introduce yourself!">Hello World!!!</Modal>
