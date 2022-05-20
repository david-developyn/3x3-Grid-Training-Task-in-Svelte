<section>
	<form action="javascript:" on:submit="{check_login}">
		<label for="username">Username (hint: "username"):</label>
		<input id="username" type="text" bind:value={username} />
		<label for="password">Password (hint: "password" case-sensitive):</label>
		<input id="password" type="password" bind:value={password} />
		<input type="submit" value="Log In" />
	</form>
	{#if success}
		<div>Login successful!</div>
	{/if}
</section>

<script>
	let username = "", password;
	let success = false;

	function check_login() {
		if ((username.toLowerCase() === "username") && (password === "password")) {
			success = true;
		}
	}
</script>

<style>
	div {
		background-color: green;
		color: white;
	}

	form {
		text-align: center;
	}

	section {
		margin: auto 0;
	}
	
	section * {
		display: block;
		margin: auto;
		width: fit-content;
	}
</style>