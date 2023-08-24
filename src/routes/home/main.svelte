<script>
	import { goto } from '$app/navigation';

	let email;

	const onEmailSubmit = ({ keyCode }) => {
		if (keyCode === 13) {
			goto(`/contact-us?email=${email}`);
		}
	};
</script>

<section>
	<div />

	<div>
		<h1>Hello!</h1>
		<h2>I'm Crypton</h2>
		<h3>Leave your mail</h3>
		<h4>And we'll contact you</h4>
		<div>
			<!-- svelte-ignore a11y-autofocus -->
			<input type="email" bind:value={email} on:keydown={onEmailSubmit} autofocus />
		</div>
	</div>

	<div>
		<h5>Technology</h5>
		<h6>Team Lookup</h6>
	</div>
</section>

<style>
	section {
		height: 100vh;
		width: 100vw;
		background-color: #111111;
		padding: 100px 50px;
		color: #ffffff;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		box-sizing: border-box;
	}

	h1,
	h2,
	h3,
	h4,
	h5,
	h6 {
		font-family: monospace;
		font-size: 72px;
		margin: 15px 0;
	}

	h3 {
		padding-top: 25px;
	}

	h3,
	h4 {
		font-size: 24px;
	}

	h5,
	h6 {
		font-size: 16px;
	}

	input {
		height: 36px;
		width: 500px;
		background: none;
		border: none;
		outline: none;
		color: #ffffff;
		font-size: 30px;
		font-family: monospace;
		transition: 0.25s;
		box-sizing: border-box;
	}

	input:hover {
		border: 1px solid #ffffff;
	}
</style>
