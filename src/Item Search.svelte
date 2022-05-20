<section>
	<input type="text" placeholder="Search" bind:value={search_query} />
	<div>
		{#each game_list as game}
			{#if game.display}
				<div>
					<img src={game.image_source} alt={game.name}/>
					<strong>{game.name}</strong>
				</div>
			{/if}
		{/each}
	</div>
</section>

<script>
	let search_query = "";
	const game_list = [
		new game_item_search(
			"Rocket League",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co4cfe.png"
		),
		new game_item_search(
			"Elite: Dangerous",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2xs9.png"
		),
		new game_item_search(
			"Roblox",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2wnq.png"
		),
		new game_item_search(
			"Minecraft",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co49x5.png"
		),
		new game_item_search(
			"StarMade",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2rf9.png"
		),
		new game_item_search(
			"Need for Speed: Most Wanted",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co20a5.png"
		),
		new game_item_search(
			"Sea of Thieves",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co2558.png"
		),
		new game_item_search(
			"Overwatch",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co1rcb.png"
		),
		new game_item_search(
			"Star Trek Online",
			"https://images.igdb.com/igdb/image/upload/t_cover_big/co1o44.png"
		)
	]

	$: game_list.forEach(game => {
		game.display = (game.name.toLowerCase().indexOf(search_query) === -1) ? false : true;
		game_list = game_list;
	});

	function game_item_search(name, image_source) {
		this.name = name;
		this.image_source = image_source;
		this.display = true;
	}
</script>

<style>
	img {
		height: 4rem;
	}

	input {
		display: block;
		margin: auto;
	}

	section > div {
		height: calc(33vh - 1rem);
		overflow-y: scroll;
	}

	section > div > div {
		align-items: center;
		display: flex;
	}
</style>