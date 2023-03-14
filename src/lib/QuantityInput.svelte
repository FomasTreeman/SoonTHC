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

<section class="flex flex__align-center" style="width: 7rem;">
  <button
    type="button"
    class="button__icon state-link__icon"
    on:click={minusQuantity}
  >
    -
  </button>
  <p>{quantity}</p>
  <button
    type="button"
    class="button__icon state-link__icon"
    on:click={addQuantity}
  >
    +
  </button>
</section>

<style>
  .flex {
    display: flex;
    align-items: start;
    justify-content: end;
  }

  .flex__align-center {
    align-items: center;
    justify-content: space-between;
  }

  .button__icon {
    border-radius: 24px;
    font-size: medium;
    font-weight: 300;
    width: 2rem;
    height: 2rem;
  }

  .state-link__icon {
    background-color: transparent;
    color: #3f51b5;
    border: 1px solid #3f51b5;
  }
</style>
