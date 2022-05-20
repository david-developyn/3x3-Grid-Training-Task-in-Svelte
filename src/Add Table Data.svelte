<form action="javascript:" on:submit={add_name_age}>
	<div>
		<label for="first_name">First Name:</label>
		<input id="first_name" type="text" />
	</div>
	<div>
		<label for="last_name">Last Name:</label>
		<input id="last_name" type="text" />
	</div>
	<div>
		<label for="age">Age:</label>
		<input id="age" type="number" />
	</div>
	<input type="submit" value="ADD" />
</form>

<script>
	import { createEventDispatcher } from "svelte";

	const dispatch = createEventDispatcher();

	function add_name_age() {
		const first_name_element = document.getElementById("first_name");
		const last_name_element = document.getElementById("last_name");
		const age_element = document.getElementById("age");
		dispatch("new_name_age", {
			first_name: first_name_element.value,
			last_name: last_name_element.value,
			age: age_element.value
		});
		first_name_element.value = "";
		last_name_element.value = "";
		age_element.value = "";
	}
</script>

<style>
	form {
		margin: auto 0;
		text-align: center;
	}

	form * {
		display: block;
		margin: auto;
	}
</style>