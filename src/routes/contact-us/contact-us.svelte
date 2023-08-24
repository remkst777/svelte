<script>
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';

	let email, description;

	onMount(() => {
		const urlParams = new URLSearchParams(window?.location?.search);
		email = urlParams.get('email');
	});

	const onSubmit = () => {
		alert(`It was sent ${JSON.stringify({ email, description })}`);
		goto('/');
	};
</script>

<section>
	<form on:submit|preventDefault={onSubmit}>
		<h1>Contact Us</h1>
		<input type="email" bind:value={email} />
		<textarea cols="30" rows="10" bind:value={description} required />
		<button type="submit">Submit</button>
	</form>
</section>

<style>
	section {
		width: 100vw;
		height: 100vh;
		padding: 100px 50px;
		display: flex;
		align-items: center;
		justify-content: center;
		font-family: monospace;
		box-sizing: border-box;
	}

	form {
		display: flex;
		flex-direction: column;
		justify-content: center;
		width: 500px;
	}

	h1 {
		font-size: 30px;
	}

	input,
	textarea,
	button {
		margin-bottom: 20px;
		outline: none;
		font-family: monospace;
		font-size: 24px;
	}

	button {
		cursor: pointer;
	}
</style>
