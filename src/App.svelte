<script>
  import AddPersonForm from "./AddPersonForm.svelte";
  import Latihan from "./Latihan.svelte";
  import Modal from "./Modal.svelte";

  let showModal = false;

  let people = [
    { name: "Bintang", beltColour: "black", age: 19, id: 1 },
    { name: "Fery", beltColour: "black", age: 19, id: 2 },
    { name: "Salim", beltColour: "black", age: 19, id: 3 },
  ];

  const openModal = () => {
    showModal = !showModal;
  };

  const addPerson = (e) => {
    const person = e.detail;
    people = [person, ...people];
    showModal = false;
  };
</script>

<main>
  <button on:click={openModal}>Open Modal</button>
  <Modal
    message="Ini adalah pesan dari props"
    isPromo={true}
    {showModal}
    on:click={openModal}
  >
    <div slot="title">
      <h3>Add a New Person</h3>
    </div>
    <AddPersonForm on:addPerson={addPerson} />
  </Modal>
  <Latihan {people} />
</main>

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
