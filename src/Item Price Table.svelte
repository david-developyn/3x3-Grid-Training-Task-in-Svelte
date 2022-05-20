<table>
	<thead>
		<tr>
			<th></th>
			<th scope="col">ITEM</th>
			<th scope="col">PRICE</th>
		</tr>
	</thead>
	<tbody>
		{#each active_item_list as item}
			<tr>
				<td>
					<input type="checkbox" bind:checked={item.active} />
				</td>
				<th scope="row">{item.name}</th>
				<td>£{item.price}</td>
			</tr>
		{/each}
	</tbody>
	<tfoot>
		<tr>
			<th scope="row" colspan="2">TOTAL</th>
			<td>£{total_price()}</td>
		</tr>
	</tfoot>
</table>

<script>
	const active_item_list = [
		new item("Item 1"),
		new item("Item 2"),
		new item("Item 3"),
		new item("Item 4"),
		new item("Item 5"),
		new item("Item 6")
	];

	$: total_price = () => {
		let total = 0;
		active_item_list.forEach(item => total += item.active ? item.price : 0);
		return total;
	}
	
	function item(name) {
		this.name = name;
		this.price = Math.ceil(Math.random() * 10);
		this.active = false;
	}
</script>

<style>
	table, th, td {
		border: 0.1rem solid black;
		margin: auto 0;
		text-align: center;
	}
</style>