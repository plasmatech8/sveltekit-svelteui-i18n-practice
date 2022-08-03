<script lang="ts">
	import { Button, Title, Text, Modal, TypographyProvider, Divider } from '@svelteuidev/core';
</script>

<Title order={1} mb="lg">Typography</Title>
<Divider variant="dashed" labelPosition="center">
	<div slot="label">Examples</div>
</Divider>

<!-- No provider -->
<h2>Typography (h2)</h2>
<p>Here is some text. Woo.</p>

<!-- Provider + vanilla HTML -->
<TypographyProvider>
	<h2>Typography (h2)</h2>
	<p>Here is some text. Woo.</p>
</TypographyProvider>

<!-- Provider + Title + Text -->
<TypographyProvider>
	<Title order={2} mb="lg">Typography (h2)</Title>
	<Text mb="lg">Here is some text. Woo.</Text>
</TypographyProvider>

<Divider variant="dashed" labelPosition="center">
	<div slot="label">Junk</div>
</Divider>

<!-- Junk -->
<div class="my-5">Text Content:</div>
<p class="text-6xl mb-5">6xl Text</p>
<Title>This is a SvelteUI Title</Title>
<h1>This is a H1 Title</h1>
