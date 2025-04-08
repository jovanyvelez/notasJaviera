<script>
	let { children } = $props();
	import '../app.css';
</script>
<div class="flex flex-col min-h-screen mx-5">
	<header class="bg-blue-500 text-white px-6 py-4 flex justify-between items-center flex-wrap">
		<h1 class="text-2xl font-bold">IE Javiera Londoño</h1>
		<nav class="mt-2 sm:mt-0">
			<a href="/" class="ml-4 hover:underline">Inicio</a>
			<a href="/decimo" class="ml-4 hover:underline">Decimo 3</a>
			<span class="ml-4 hover:underline disabled:opacity-50">Once 3</span>
		</nav>
	</header>
	<main class="flex-grow  mx-auto my-8">
		{@render children()}
	</main>
	<footer class="bg-gray-100 text-gray-700 text-center py-4 text-sm mt-auto">
		<p>&copy; {new Date().getFullYear()} - Profesor/a Jovany Vélez</p>
		<p class="mt-1">Todos los derechos reservados</p>
	</footer>
</div>
