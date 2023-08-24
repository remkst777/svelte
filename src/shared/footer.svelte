<script>
	let color;
	const year = new Date().getFullYear();

	$: {
		const { isScrolled, isHome } = $$props;
		color = isScrolled || !isHome ? '#ff0000' : '#ffffff';
	}
</script>

<footer style="--color: {color}">{year}</footer>

<style>
	footer {
		position: fixed;
		top: calc(100vh - 100px);
		width: 100%;
		height: 100px;
		padding: 20px 50px;
		text-align: end;
		color: var(--color);
		box-sizing: border-box;
		font-size: 24px;
		font-family: monospace;
	}
</style>
