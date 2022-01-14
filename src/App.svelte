<script lang="ts">
	let doseLength: number;
	let dosesPerDay: number;
	let startDate: string;
	let startDoses: number;

	const onSubmit: svelte.JSX.FormEventHandler<HTMLFormElement> = () => {
		console.log('length', doseLength)
		console.log('per day', dosesPerDay)
		console.log('start', startDate)
		console.log('start doses', startDoses)
	}
</script>

<main>
	<form on:submit|preventDefault={onSubmit}>
		<label for="dose-length">Dose Length in Days</label>
		<input type="number" id="dose-length" min="1" required bind:value={doseLength}>

		<label for="doses-per-day">Doeses per Day</label>
		<input type="number" id="doses-per-day" min="1" required bind:value={dosesPerDay}>

		<label for="start-date">Start Date</label>
		<input type="date" id="start-date" required bind:value={startDate}>

		<label for="start-doses">Doses on Start Date</label>
		<input type="number" id="start-doses" min="1" required bind:value={startDoses}>

		<button type="reset">Reset</button>
		<button type="submit">Go</button>
	</form>
</main>
