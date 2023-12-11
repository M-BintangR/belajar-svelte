<script>
  import { createEventDispatcher } from "svelte";

  let dispatch = createEventDispatcher({});

  let name;
  let beltColour;
  let age;

  let skills = [];

  const handleSubmit = () => {
    const person = {
      name,
      beltColour,
      age,
      skills,
      id: Math.random(),
    };
    dispatch("addPerson", person);
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="Name" bind:value={name} />
  <input type="number" bind:value={age} />

  <label for="">Skills : </label>
  <input type="checkbox" bind:group={skills} value="reading" />Reading <br />
  <input type="checkbox" bind:group={skills} value="coding" />Coding <br />
  <input type="checkbox" bind:group={skills} value="studying" />Studying <br />
  <input type="checkbox" bind:group={skills} value="jogging" />Jogging <br />
  <input type="checkbox" bind:group={skills} value="sports" />Sports <br />

  <label for="">Belt Colour : </label>
  <select bind:value={beltColour}>
    <option value="black">black</option>
    <option value="orange">orange</option>
    <option value="brown">brown</option>
    <option value="white">white</option>
  </select>

  <button>Add Person</button>
</form>

<style>
</style>
