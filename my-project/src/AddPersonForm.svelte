<script>
    import {createEventDispatcher} from 'svelte'
    const dispatch  = createEventDispatcher()

    let name
    let age
    let beltcolor

    let skills=  []
    const handleSubmit = () => {
        const person = {
            name,
            age,
            beltcolor,
            skills,
            id: Math.random()*10
        }

        dispatch('addPerson', person)
    }


</script>

<form on:submit|preventDefault={handleSubmit}> 
	<input type="text" placeholder="name" bind:value={name}>
	<input type="number" placeholder="age" bind:value={age}>

    <label>Skills:</label>
    <input type="checkbox" bind:group={skills} value='fighting'> fighting <br>
    <input type="checkbox" bind:group={skills} value='running'> running <br>
    <input type="checkbox" bind:group={skills} value='loving'> loving <br>

    <label>Belt Color:</label>
    <select bind:value={beltcolor}>
        <option value="red">Red</option>
        <option value="green">Green</option>
        <option value="orange">Orange</option>
    </select>

	<button>Add Person</button>
</form>

<style>
</style>