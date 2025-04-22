<script lang="ts">
	import { createHighlighter } from 'shiki';

	let html = '';
	async function main() {
		const highlighter = await createHighlighter({
			themes: ['vitesse-dark'],
			langs: ['javascript']
		});

		html = highlighter.codeToHtml(`console.log('Hello, world!')`, {
			lang: 'ts',
			theme: 'poimandres'
		});
	}
</script>

{html}
