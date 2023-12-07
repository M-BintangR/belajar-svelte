<script>
  let name = "Muhammad Bintang";
  let beltColour = "Black";

  const handleClick = () => {
    beltColour = "Orange";
  };

  const handleInput = (e) => {
    beltColour = e.target.value;
  };
</script>

<main>
  <h1>Hello {name}!</h1>
  <p style="color: {beltColour};">
    Color {beltColour}
  </p>
  <button on:click={handleClick}>Update Color</button>
  <!-- <input type="text" on:input={handleInput} value={beltColour} /> -->
  <input type="text" bind:value={beltColour} />
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
