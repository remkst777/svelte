<script>
	import { goto } from '$app/navigation';

	let items = [];

	fetch('https://jsonplaceholder.typicode.com/albums/1/photos')
		.then((response) => response.json())
		.then((data) => (items = data));

	const onSeeMore = () => goto('/see-more');
</script>

<ul>
	{#each items.slice(0, $$props.isHome ? 5 : undefined) as { title, url }}
		<li>
			<h3>{title}</h3>
			<img src={url} alt="" />
		</li>
	{/each}

	{#if $$props.isHome}
		<div class="see-more" on:click={onSeeMore}>See more</div>
	{/if}
</ul>

<style>
	ul {
		list-style: none;
		display: flex;
		flex-direction: column;
		align-items: center;
		font-family: monospace;
		padding: 100px 0;
	}

	li {
		padding: 30px;
	}

	.see-more {
		text-align: center;
		font-family: monospace;
		font-size: 24px;
		padding: 30px;
		cursor: pointer;
	}
</style>
