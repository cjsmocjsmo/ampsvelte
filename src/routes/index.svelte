<script >
	import { onMount } from 'svelte';
// import Album from './album.svelte';

	let artists = [];

	onMount(async () => {
		const ress = await fetch(`http://192.168.0.91:9090/InitArtistInfo2`);
		artists = await ress.json();
		
		console.log(artists);
	});

	let show = false;

	const handleClick = () => {
		if (show === true) {
			show = false
		} else {
			show = true
		}
	}
</script>

<svelte:head>
	<title>Artists</title>
</svelte:head>

<h1>Artists</h1>
{#each artists as art }
	<div class="artistflexbox">
		<div class="artistflex">
			<h3>{art.Artist}</h3>
			<h5>{art.Albums.length} albums</h5>
		</div>
		<span on:click={handleClick} >+</span>
	</div>
	{#if show }
		<div current={art.id}>
			{#each art.Albums as alb}
				<h3>{alb.album}</h3>
			{/each}
		</div>
	{:else}
		<div></div>
	{/if}
	
	<hr />
{/each}

<style>
	hr {
		border: 0;
		border-top: 2px solid brown;
		width: 100%;
    }
	span {
        font-size: 2em;
    }
	.artistflexbox {
        display: flex;
        flex: 1;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
	.artistflex {
		display: flex;
		flex: 1;
		flex-direction: column;
		align-items: left;
	}

</style>
