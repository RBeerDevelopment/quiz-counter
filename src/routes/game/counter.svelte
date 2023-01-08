<script lang="ts">
	export let score: number;
	export let index: number;
	export let increment: () => void;
	export let decrement: () => void;
</script>

<p class="text-2xl p-4">Runde {index + 1}</p>
<div class="flex justify-around text-3xl h-20">
	<button on:click={decrement} class="w-2/5">-</button>
	<div class="h-full flex items-center">
		<p>{score}</p>
	</div>
	<button on:click={increment} class="w-2/5">+</button>
</div>
