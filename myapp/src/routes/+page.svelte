<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	
	let name = '';
	let a = 0;
	let b = 1;


	let text = `Some words are *italic*, some are **bold**`;

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>
		<span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</span>

		to your new<br />SvelteKit app 
	</h1>

	<h2>
		try editing <strong>src/routes/+page.svelte</strong>
	</h2>

	<Counter />
</section>

<section>
	<input bind:value={name} placeholder="Enter your Philosophy Question">
	<p> {name}</p>

</section>

<label>
	<input type=number bind:value={a} min=0 max=1 step=.1>
	<input type=range bind:value={a} min=0 max=1 step=.1>
</label>

<label>
	<input type=number bind:value={b} min=0 max=1 step = .1>
	<input type=range bind:value={b} min=0 max=1 step = .1>
</label>

<p>{a} + {b} = {a + b}</p>



<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}

	textarea { width: 100%; height: 200px; }
</style>
