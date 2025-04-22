<script>
	import rehypeShiki from '@shikijs/rehype';
	import rehypeStringify from 'rehype-stringify';
	import remarkParse from 'remark-parse';
	import remarkRehype from 'remark-rehype';
	import { unified } from 'unified';

	let markdown = `
\`\`\`svelte {2,6} showLineNumbers
<script>
	let banana = $state('🍌')
<\/script>

# Mi nombre es banana

<button onclick={() => banana += '🍌'}>
	{banana}
</button>
\`\`\`
  `;

	let html = '';

	(async () => {
		const file = await unified()
			.use(remarkParse)
			.use(remarkRehype)
			.use(rehypeShiki, {
				// or `theme` for a single theme
				themes: {
					light: 'poimandres',
					dark: 'vitesse-dark'
				}
			})
			.use(rehypeStringify)
			.process(markdown);
		html = String(file);
		console.log(html);
	})();
</script>

{@html html}