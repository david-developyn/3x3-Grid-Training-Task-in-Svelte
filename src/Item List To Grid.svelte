<section>
	<button on:click={() => {show_name = !show_name;}}>Change Display</button>
	<div class={show_name ? "list" : "grid"}>
		{#each game_list as game}
			<div>
				<img src={game.image_source} alt={game.name} />
				{#if show_name}
					<strong>{game.name}</strong>
				{/if}
			</div>
		{/each}
	</div>
</section>

<script>
	const game_list = [
		new game_item_list_to_grid(
			"Rocket League",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co4cfe.png"
		),
		new game_item_list_to_grid(
			"Elite: Dangerous",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2xs9.png"
		),
		new game_item_list_to_grid(
			"Roblox",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2wnq.png"
		),
		new game_item_list_to_grid(
			"Minecraft",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co49x5.png"
		),
		new game_item_list_to_grid(
			"StarMade",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2rf9.png"
		),
		new game_item_list_to_grid(
			"Need for Speed: Most Wanted",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co20a5.png"
		),
		new game_item_list_to_grid(
			"Sea of Thieves",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2558.png"
		),
		new game_item_list_to_grid(
			"Overwatch",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co1rcb.png"
		),
		new game_item_list_to_grid(
			"Star Trek Online",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co1o44.png"
		)
	];
	let show_name = true;

	function game_item_list_to_grid(name, image_source) {
		this.name = name;
		this.image_source = image_source;
		this.display = true;
	}
</script>

<style>
	button {
		display: block;
		margin-left: auto;
	}

	img {
		height: 4rem;
	}

	section {
		margin: auto 0;
	}

	section > div > div {
		align-items: center;
		display: flex;
	}

	.grid {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		margin: auto;
		width: fit-content;
	}

	.list {
		overflow-y: scroll;
		height: calc(33vh - 1rem);
	}
</style>