<script lang="ts">
	import { page } from '$app/stores';
	import Counter from './counter.svelte';

	const roundsQueryParam = $page.url.searchParams.get('rounds');
	const numberOfRounds = roundsQueryParam ? parseInt(roundsQueryParam) : 3;

	let scores = new Array(numberOfRounds).fill(0) as number[];

	$: overallScore = scores.reduce((accumulator, current) => accumulator + current, 0);
	function decrement(index: number) {
		const cloned = [...scores];
		if (cloned[index] > 0) {
			cloned[index] = cloned[index] - 1;
		}
		scores = cloned;
	}

	function increment(index: number) {
		const cloned = [...scores];
		cloned[index] = cloned[index] + 1;
		scores = cloned;
	}
</script>

{#each scores as score, index}
	<Counter {score} {index} increment={() => increment(index)} decrement={() => decrement(index)} />
{/each}

<p class="text-3xl py-8 w-full text-center">
	Gesamt: {overallScore}
</p>
