<main>
	<DigitalClock />
	<LoginForm />
	<Quiz />
	<Name_Age_Table name_age_table={name_age_table} />
	<Add_Table_Data on:new_name_age={add_new_name_age_to_table} />
	<Item_Price_Table />
	<Item_Search />
	<Item_List_To_Grid />
	<Magic_8Ball />
</main>

<script>
	import DigitalClock from "./Digital Clock.svelte";
	import LoginForm from "./Login Form.svelte";
	import Quiz from "./Quiz.svelte";
	import Name_Age_Table from "./Name Age Table.svelte";
	import Add_Table_Data from "./Add Table Data.svelte";
	import Item_Price_Table from "./Item Price Table.svelte";
	import Item_Search from "./Item Search.svelte";
	import Item_List_To_Grid from "./Item List To Grid.svelte";
	import Magic_8Ball from "./Magic 8-ball.svelte";

	let name_age_table = [];

	function add_new_name_age_to_table(name_age) {
		name_age_table = [...name_age_table, name_age.detail];
	}
</script>

<style>
	main {
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		grid-template-rows: 1fr 1fr 1fr;
		height: 100vh;
		overflow: hidden;
	}
</style>