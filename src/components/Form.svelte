<script>
import { createEventDispatcher } from "svelte";
    let dispatch = createEventDispatcher()

    let name;
    let eyeColor;
    let age;
    
    let skills = [
    
    ]
    
    const handleSubmit = () => {
        const person = {
            name,
            eyeColor,
            age,
            skills,
            id: Math.random()
        }

        dispatch('addPerson', person)
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" bind:value={age}>
    <label for="skills">Skills</label>
    
    <input type="checkbox" bind:group={skills} value="figting">Fighting <br>
    <input type="checkbox" bind:group={skills} value="computerSince">Computer Since <br>
    <input type="checkbox" bind:group={skills} value="sneaking">Sneaking <br>
    <input type="checkbox" bind:group={skills} value="skying">Skying <br>
    
    <label for="">Eye Color :</label>
    <select bind:value={eyeColor}>
        <option value="black">Black</option>
        <option value="white">White</option>
        <option value="yellow">Yellow</option>
        <option value="green">Green</option>
    </select><br>

    <button type="submit">Add Person</button>
</form>

<style>
    
</style>