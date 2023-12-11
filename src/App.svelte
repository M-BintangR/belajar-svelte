<script>
  import Latihan from "./Latihan.svelte";
  import Modal from "./Modal.svelte";

  let showModal = false;

  const openModal = () => {
    showModal = !showModal;
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
    
    <form action="">
      <input type="text" placeholder="Name" />
      <input type="text" placeholder="Belt Colour" />
      <button>Add Person</button>
    </form>
  </Modal>
  <Latihan />
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
