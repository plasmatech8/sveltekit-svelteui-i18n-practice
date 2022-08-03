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
