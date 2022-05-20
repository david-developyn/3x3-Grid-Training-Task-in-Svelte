<section>
	<form action="javascript:" on:submit={get_answer}>
		<input type="text" bind:value={question} />
		<input type="submit" value="Ask" />
	</form>
	<img id="magic_8ball_back" src="Magic 8-ball (Back).png" alt="Magic 8-ball" class:shake_magic_8ball_back={shaking} />
	<img id="magic_8ball_front" src="Magic 8-ball (Front).png" alt="Magic 8-ball" class:shake_magic_8ball_front={shaking} />
	<strong id="magic_8ball_answer" class:shake_magic_8ball_answer={shaking}>{answer}</strong>
</section>

<script>
	let question = "";
	let answer = "";
	const possible_answers = [
		"It is certain",
		"It is decidedly so",
		"Without a doubt",
		"Yes definitely",
		"You may rely on it",
		"As I see it, yes",
		"Most likely",
		"Outlook good",
		"Yes",
		"Signs point to yes",
		"Reply hazy, try again",
		"Ask again later",
		"Better not tell you now",
		"Cannot predict now",
		"Concentrate and ask again",
		"Don't count on it",
		"My reply is no",
		"My sources say no",
		"Outlook not so good",
		"Very doubtful"
	];
	let shaking = false;
	
	function get_answer() {
		if (!question) {
			return;
		}
		restart_animation(document.getElementById("magic_8ball_front"));
		restart_animation(document.getElementById("magic_8ball_back"));
		restart_animation(document.getElementById("magic_8ball_answer"));
		shaking = true;
		answer = possible_answers[Math.floor(Math.random() * possible_answers.length)];
	}

	function restart_animation(element) {
		element.style.animation = "none";
		element.offsetHeight;
		element.style.animation = null; 
	}
</script>

<style>
	form {
		text-align: center;
	}

	img {
		position: absolute;
		top: 2rem;
		height: calc(33vmin - 2rem);
	}

	section {
		display: flex;
		justify-content: center;
		margin: 0;
		position: relative;
	}

	strong {
		color: white;
		display: flex;
		font-size: 0.9rem;
		justify-content: center;
		position: absolute;
		text-align: center;
		top: 10rem;
		width: 5rem;
	}

	.shake_magic_8ball_answer {
		animation:
			shake_animation 250ms 25,
			fade 5s both reverse;
	}

	.shake_magic_8ball_back {
		animation: shake_animation 250ms 25;
	}

	.shake_magic_8ball_front {
		animation:
			shake_animation 250ms 25,
			fade 5s both;
	}

	@keyframes fade {
		from {
			opacity: 100%;
		}
		to {
			opacity: 0;
		}
	}

	@keyframes shake_animation {
		0% {
			transform: translate(0);
		}
		25% {
			transform: translate(-10rem);
		}
		75% {
			transform: translate(10rem);
		}
		100% {
			transform: translate(0);
		}
	}
</style>