<script>
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
	import Playercontrols from'../lib/player/playercontrols.svelte'
	let show = true;
	const handleClick = () => {
		if (show === true) {
			show = false;
		} else {
			show = true;
		}
	}

</script>

<Header />

<audio class="Audio1" controls=true style="width: 100%; margin-top: 10px"></audio>


<Playercontrols />

<main>
	<slot />
</main>



<footer>
	
	<!-- <p>Possible player controls</p> -->
</footer>
<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	footer{
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>
