<strong>{ Time }</strong>

<script>
	let Time = new Date().toLocaleTimeString();
	window.setInterval(() => {
			Time = new Date().toLocaleTimeString();
	}, 1000);
</script>

<style>
	strong {
		margin: auto;
	}
</style>