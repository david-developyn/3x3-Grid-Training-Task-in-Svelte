<table>
	<thead>
		<tr>
			<th>First Name</th>
			<th>Last Name</th>
			<th>Age</th>
		</tr>
	</thead>
	<tbody>
		{#each name_age_table as row, row_index}
			<tr>
				<td>{row.first_name}</td>
				<td>{row.last_name}</td>
				<td>{row.age}</td>
				<td>
					<button on:click={() => delete_row(row_index)}>DELETE</button>
				</td>
			</tr>
		{/each}
	</tbody>
</table>

<script>
	export let name_age_table;

	function delete_row(row_index) {
		name_age_table.splice(row_index, 1);
		name_age_table = name_age_table;
	}
</script>

<style>
	button {
		border: none;
	}

	table, th, td {
		border: 0.1rem solid black;
		margin: auto 0;
		text-align: center;
	}
</style>