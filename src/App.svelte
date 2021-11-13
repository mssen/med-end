<script lang="ts">
	interface FormValues {
		doseLength?: number;
		dosesPerDay?: number;
		startDate?: string;
		startDoses?: number;
	}

	let formValues: FormValues = {};

	const onSubmit: svelte.JSX.FormEventHandler<HTMLFormElement> = ({ currentTarget }) => {
		formValues.doseLength = currentTarget['dose-length'].value;
		formValues.dosesPerDay = currentTarget['doses-per-day'].value;
		formValues.startDate = currentTarget['start-date'].value;
		formValues.startDoses = currentTarget['start-doses'].value;

		console.log(formValues)
	}


</script>

<main>
	<form on:submit|preventDefault={onSubmit}>
		<label for="dose-length">Dose Length in Days</label>
		<input type="number" id="dose-length" min="1" required bind:value={formValues.doseLength}>

		<label for="doses-per-day">Doeses per Day</label>
		<input type="number" id="doses-per-day" min="1" required bind:value={formValues.dosesPerDay}>

		<label for="start-date">Start Date</label>
		<input type="date" id="start-date" required bind:value={formValues.startDate}>

		<label for="start-doses">Doses on Start Date</label>
		<input type="number" id="start-doses" min="1" required bind:value={formValues.startDoses}>

		<button type="reset">Reset</button>
		<button type="submit">Go</button>
	</form>
</main>
