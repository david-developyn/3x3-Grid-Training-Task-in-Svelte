<form action="javascript:" on:submit={check_answers}>
	{#each user_answers as answer, index_1}
		<fieldset>
			<legend>Question {index_1 + 1} (hint: {index_1 + 1})</legend>
			{#each Array(4) as option, index_2}
				<div>
					<input id="question_{index_1 + 1}-answer_{index_2 + 1}" type="radio" name="question_{index_1 + 1}" on:input={() => change_answer(index_1, index_2 + 1) } />
					<label for="question_{index_1 + 1}-answer_{index_2 + 1}">{index_2 + 1}</label>
				</div>
			{/each}
		</fieldset>
	{/each}
	<input type="submit" />
</form>

<script>
	let completed_quiz_sound = document.createElement("audio");
	let user_answers = [0, 0, 0, 0];

	function change_answer(question_id, answer_id) {
		user_answers[question_id] = answer_id;
	}

	function check_answers() {
		const correct_answers = [1, 2, 3, 4];
		for (let index = 0; index < user_answers.length; index++) {
			if (user_answers[index] !== correct_answers[index]) {
				return;
			}
		}
		completed_quiz_sound.src = "https://interactive-examples.mdn.mozilla.net/media/cc0-audio/t-rex-roar.mp3";
		completed_quiz_sound.play();
	}
</script>

<style>
	div {
		display: inline-block;
		margin: 0 1rem;
		margin-bottom: 0.5rem;
	}

	form {
		margin: auto 0;
		text-align: center;
	}
</style>