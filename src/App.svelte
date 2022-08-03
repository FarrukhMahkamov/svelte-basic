<script>
	import Modal from './components/Modal.svelte'

	let showModal = false
	const toggleModal = () => {
		showModal = !showModal
	}
	let people = [
		{id : 1,name : "Farruh",eyeColor : "Black",age : 22},
		{id : 2,name : "Umid",eyeColor : "Green",age : 22},
		{id : 3,name : "Ozod",eyeColor : "Black",age : 18}
	]

	const removePerson = (id) => {
		people = people.filter((data) => data.id != id)
	}
</script>
<Modal message="Hey its a prop" isPromo={true} {showModal} on:click={toggleModal}/>
<main>
	<button on:click={toggleModal}>Open Modal</button>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			<p>{person.age}, color of the eye {person.eyeColor}</p>
			<button on:click={() => {removePerson(person.id)}}>Delete</button>
		</div>
		{:else}
		<p>There is no peaople to show</p>
	{/each}
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