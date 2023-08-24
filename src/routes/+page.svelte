<script>
	import Header from '../shared/header.svelte';
	import Home from './home/home.svelte';
	import Footer from '../shared/footer.svelte';

	let scrollY, isScrolled;

	$: {
		isScrolled = !!scrollY;
	}
</script>

<Header {isScrolled} isHome />
<Home />
<Footer {isScrolled} isHome />

<svelte:window bind:scrollY />
