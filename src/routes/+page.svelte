<script lang="ts">
	let rounds = 3;

	function increment() {
		rounds += 1;
	}

	function decrement() {
		if (rounds <= 0) return;
		rounds -= 1;
	}
</script>

<div class="w-full h-full pt-16 flex flex-col items-center justify-evenly text-lg">
	<p>Anzahl Runden:</p>
	<div class="flex w-1/2 justify-evenly text-3xl h-20">
		<button class="w-2/5" on:click={decrement}>-</button>
		<div class="h-full flex items-center">
			<p>{rounds}</p>
		</div>
		<button class="w-2/5" on:click={increment}>+</button>
	</div>
	<a class="bg-[#b75957] py-2 px-4 text-white rounded-lg" href={`/game?rounds=${rounds}`}>Start</a>
</div>
