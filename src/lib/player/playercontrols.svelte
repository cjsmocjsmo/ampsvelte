<script>
	let show = true;
	const handleClick = () => {
		if (show === true) {
			show = false;
		} else {
			show = true;
		}
	}
</script>

<div class="playermain">
	<div id="playerDiv">
		<svg id="previous" xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-dash-lg" viewBox="0 0 16 16">
			<path d="M0 8a1 1 0 0 1 1-1h14a1 1 0 1 1 0 2H1a1 1 0 0 1-1-1z"/>
		</svg>
		<!-- <button id="playerbtn1">PR</button> -->
		{#if show }
			<svg id="playarrow" on:click={handleClick} xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-play-fill" viewBox="0 0 16 16">
				<path d="m11.596 8.697-6.363 3.692c-.54.313-1.233-.066-1.233-.697V4.308c0-.63.692-1.01 1.233-.696l6.363 3.692a.802.802 0 0 1 0 1.393z"/>
			</svg>
			<!-- <button id="playerbtn1" on:click={handleClick}>Play</button> -->
		{:else}
			<svg id="pause" on:click={handleClick} xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-pause" viewBox="0 0 16 16">
				<path d="M6 3.5a.5.5 0 0 1 .5.5v8a.5.5 0 0 1-1 0V4a.5.5 0 0 1 .5-.5zm4 0a.5.5 0 0 1 .5.5v8a.5.5 0 0 1-1 0V4a.5.5 0 0 1 .5-.5z"/>
			</svg>
		
			<!-- <button id="playerbtn1" on:click={handleClick}>Pause</button> -->
		{/if}
		<svg id="add" xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="currentColor" class="bi bi-plus" viewBox="0 0 16 16">
			<path d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z"/>
		</svg>
		<!-- <button id="playerbtn1">NE</button> -->
	</div>
</div>

<style>
	.playermain {
		margin: 1em 1em 0 1em
	}
	#playerDiv {
		display: flex;
		flex: 1;
		flex-direction: row;
		justify-content: space-between;
		width: 100%;
	}
	/* #playerbtn1 {
		display: block;
		padding: 5px;
		border-radius: 50%;
  		border: 1px solid green;

	} */
</style>