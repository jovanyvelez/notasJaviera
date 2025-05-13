
<script>
	let { children } = $props();

</script>


<div>
	<header>
		<h1>IE Javiera Londoño</h1>
		<nav>
			<a href="/" >Inicio</a>
			<a href="/decimo">Decimo 3</a>
			<a href="/once" >Once 3</a>
		</nav>
	</header>
	<main >
		{@render children()}
	</main>
	<footer >
		<p>&copy; {new Date().getFullYear()} - Profesor/a Jovany Vélez</p>
		<p>Todos los derechos reservados</p>
	</footer>
</div>



<style>
	@reference "tailwindcss";

	div {
		@apply flex flex-col min-h-screen mx-5 rounded-md;

		header {
			@apply bg-blue-500 text-white px-6 py-4
				flex flex-col justify-between items-center flex-wrap
				rounded-xl ;

			h1 {
				@apply text-3xl text-center sm:text-left md:text-5xl font-bold;
			}
			nav {
				@apply  mt-2 sm:mt-0 text-xl sm:text-2xl;

				a{
					@apply ml-4 text-amber-50 hover:text-blue-500 rounded-sm hover:bg-amber-50;
					text-decoration: none;
				}

			}
		}
		footer {
			@apply bg-gray-100 text-gray-700 text-center py-4 text-sm mt-auto;
			p {
				@apply mt-1;
			}
		}
	}


	main {
		@apply flex-grow mx-2 sm:mx-10 md:mx-14 lg:mx-20  my-8;
	}

</style>
