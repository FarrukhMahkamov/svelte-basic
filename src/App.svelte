<script>
	let firstName = 'Farruh'
	let lastName = 'Mahkamov'

	$: fullname = `${firstName} ${lastName}`

</script>

<main>
	<p>Your name is {firstName}</p>
	<p>Your last name is {lastName}</p>

	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>