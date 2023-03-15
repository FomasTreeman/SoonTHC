<script>
  export let maxQuantity;
  export let quantity;

  function addQuantity() {
    if (quantity < maxQuantity) quantity += 1;
  }

  function minusQuantity() {
    if (quantity > 0) quantity -= 1;
  }
</script>

<section class="flex align-center">
  <button type="button" on:click={minusQuantity}> - </button>
  <p>{quantity}</p>
  <button type="button" on:click={addQuantity}> + </button>
</section>

<style>
  section {
    width: 7rem;
  }

  .flex {
    display: flex;
    align-items: start;
    justify-content: end;
  }

  .align-center {
    align-items: center;
    justify-content: space-between;
  }

  button {
    font-size: medium;
    font-weight: 300;
    width: 2rem;
    height: 2rem;
    background-color: transparent;
    color: #3f51b5;
    border: 1px solid #3f51b5;
    border-radius: 24px;
  }
</style>
