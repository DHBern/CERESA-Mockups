<script lang="ts">
	import { base } from '$app/paths';

	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();

	let fassung = $state('LF');
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<nav class="fixed top-5 left-5 flex flex-wrap gap-x-10 font-bold">
	<a href={`${base}/eloisa1`}>Eloisa frammento 1</a>
	<a href={`${base}/eloisa2`}>Eloisa frammento 2</a>
	<a href={`${base}/poesie`}>Poesie</a>
	<a href={`${base}/adamo`}>Adamo</a>
	<a href={`${base}/anima`}>Anima</a>
	<a href={`${base}/aborto`}>Aborto</a>
	<a href={`${base}/carson`}>Carson McCullers</a>
</nav>

<button
	onclick={() => {
		fassung = fassung == 'DF' ? 'LF' : 'DF';
	}}
	class={['font-bold pointer fixed top-30 left-20 rounded-xl p-2 px-5', fassung=='DF' ? 'bg-red-200' : 'bg-blue-200']}
	>{fassung == 'DF' ? 'change to LF' : 'change to DF'}</button
>

<div data-fassung={fassung} class="max-w-250 mx-auto mt-50">
	{@render children()}
</div>
