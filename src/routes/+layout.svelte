<script>
	import '../app.css';
	import { page } from '$app/stores';

	$: isHome = $page.url.pathname === '/';
	console.log($page.url.pathname, isHome);
</script>

<section class="h-14 w-full bg-[#b75957] shadow-xl flex items-center p-4">
	{#if !isHome}
		<a href="/">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="3"
				stroke="currentColor"
				class="w-6 h-6 mr-6 text-white"
			>
				<path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
			</svg>
		</a>
	{/if}
	<p class="text-white text-3xl">Quiz Counter</p>
</section>
<slot />
