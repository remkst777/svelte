<script>
	import { goto } from '$app/navigation';

	let isRegularLogo, color, hover;

	$: {
		const { isScrolled, isHome } = $$props;
		color = isScrolled || !isHome ? '#ff0000' : '#ffffff';
	}

	$: {
		const { isScrolled, isHome } = $$props;
		hover = isHome && !isScrolled ? '#fbfb07' : '#000000';
	}

	const onToggleLogo = () => {
		if ($$props.isHome) {
			return (isRegularLogo = !isRegularLogo);
		}

		goto('/');
	};
</script>

<header style="--color: {color}; --hover: {hover};">
	<button on:click={onToggleLogo}>{isRegularLogo ? '+_+' : '=_='}</button>
	<a href="/contact-us">Contact Us</a>
</header>

<style>
	header {
		position: fixed;
		width: 100%;
		height: 100px;
		padding: 20px 50px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		box-sizing: border-box;
	}

	button,
	a {
		color: var(--color);
		font-size: 24px;
		font-family: monospace;
		cursor: pointer;
		text-decoration: none;
		transition: 0.25s;
	}

	button:hover,
	a:hover {
		color: var(--hover);
	}
</style>
