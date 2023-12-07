<script>
  let showModal = true;
  let isPromo = true;
</script>

{#if showModal}
  <div class="backdrop">
    <div class="modal" class:promo={isPromo}>
      <p>Sign Up for Offers</p>
    </div>
  </div>
{/if}

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.8);
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
  }
  .modal {
    padding: 10px;
    margin: 10% auto;
    border-radius: 10px;
    max-width: 400px;
    text-align: center;
    background: white;
  }

  .promo {
    background: crimson;
    color: white;
  }
</style>
