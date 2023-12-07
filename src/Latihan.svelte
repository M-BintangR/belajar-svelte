<script>
  //   let name = "Muhammad Bintang";
  //   let firstName = "Muhammad";
  //   let lastName = "Bintang";
  //   let beltColour = "Black";

  let people = [
    { name: "Bintang", beltColour: "black", age: 19, id: 1 },
    { name: "Fery", beltColour: "black", age: 19, id: 2 },
    { name: "Salim", beltColour: "black", age: 19, id: 3 },
  ];

  //   $: fullName = `${firstName} ${lastName}`; // Reactive value

  //   $: {
  //     console.log(beltColour);
  //     console.log(fullName);
  //   }

  //   const handleClick = () => {
  //     beltColour = "Orange";
  //   };

  //   const handleInput = (e) => {
  //     beltColour = e.target.value;
  //   };

  const deleteData = (id) => {
    people = people.filter((person) => person.id !== id);
  };

  let num = 5;
</script>

<div>
  {#if num > 20}
    <p>Number 20</p>
  {:else if num > 5}
    <p>Number 5</p>
  {:else}
    <p>Data Number 20 Or 5</p>
  {/if}

  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      <p>{person.age} years old, {person.beltColour} belt.</p>
      {#if person.beltColour == "black"}
        <p><strong>BLACK</strong></p>
      {:else}
        <p><strong>NOT BLACK</strong></p>
      {/if}
      <button on:click={deleteData(person.id)}>Delete Data</button>
    </div>
  {:else}
    <p>There are not people to show...</p>
  {/each}
  <!-- <p style="color: {beltColour};">
    {fullName}
    {beltColour} belt
  </p> -->
  <!-- <button on:click={handleClick}>Update Color</button> -->
  <!-- <input type="text" on:input={handleInput} value={beltColour} /> -->
  <!-- <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
  <input type="text" bind:value={beltColour} /> -->
</div>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
