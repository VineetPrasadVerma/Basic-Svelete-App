<script>
	import Modal from './Modal.svelte'
	import AddPersonForm from './AddPersonForm.svelte'
	// // let name = 'My First Svelte App';
	// let beltColor = 'Black'
	// let firstName = 'Vineet'
	// let lastName = 'Verma'

	// const handleClick = () =>{
	// 	beltColor = 'Orange'
	// }

	// const handleInput = (e) => {
	// 	beltColor = e.target.value
	// }

	// $:fullName =  `${firstName} ${lastName}` // reactivity

	// $: {
	// 	console.log(beltColor)
	// 	console.log(firstName)
	// }
	let showModal = false
	let persons = [
		{name:'Vineet', age:22, beltcolor:'black', id:1},
		{name:'Vikas', age:24, beltcolor:'red', id:2},
		{name:'Vinay', age:23, beltcolor:'green', id:3}
	]

	const handleShowModal = () => {
		showModal = !showModal
	}

	const handleClick = (id) => {
		persons = persons.filter(p => p.id !== id)
	}

	const addPerson = (e) => {
		persons = [...persons, e.detail]
		showModal = false
	}

</script>

<main>
	<!-- <p>{fullName} has {beltColor} Belt</p>
	<!-- <buttton on:click={handleClick}>Change Belt Color</buttton> -->
	<!-- <input type="text" on:input={handleInput} value={beltcolor}> -->
	<!-- <input type="text" bind:value={beltColor}>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}> -->
	<Modal isPromo={true} {showModal} on:click={ handleShowModal }>
		<AddPersonForm on:addPerson={addPerson}/>	
	</Modal>

	<button on:click={ handleShowModal } >Open Modal</button>

	{#each persons as person (person.id)}
		<div>
			<h4>{person.name} is {person.age} year's old</h4>
			<button on:click={(e) => handleClick(person.id) }>Delete</button>
		</div>	
	{:else}
		<p>Nothing to show</p>
	{/each}

</main>

<style>
	main {
		text-align: center;
		/* padding: 1em; */
		max-width: 240px;
		margin: 0 auto;
	}

	/* h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	} */

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>