<script>
  import QuantityInput from "../lib/QuantityInput.svelte";
  import countStore from "../store";

  let stock = 10;
  let quantity = 1;

  function setBasketCount() {
    countStore.update((x) => x + quantity);
  }
</script>

<img class="item" src="clothing.png" alt="item of clothing" />
<section class="flex column">
  <article class="description">
    <h2 class="product">Waxed Cotton Hooded Jacket</h2>
    <p>
      The Drumming jacket in orange is finished with a water-repellent dry wax
      treatment that creates a love-worn look. It's made in the United Kingdom
      using organic cotton ripstop with a drawstring hood, underarm eyelets and
      buttoned flap front pockets. Shoulder epaulettes add a utilitarian twist,
      while a fly-fronted zip and snap-button closure keeps the overall look
      streamlined. Attach one of the collection's padded liners to the internal
      tab on cooler days.
    </p>
    <p>£650</p>
  </article>

  <p class="opacity stock">{stock} IN STOCK</p>
  <QuantityInput maxQuantity={10} bind:quantity />
  <button
    type="button"
    class="button__text state-link__text"
    style="margin-block: 2rem"
    on:click={setBasketCount}
  >
    ADD TO BASKET
  </button>
</section>

<style>
  .item {
    max-width: 40%;
    margin: 5%;
    float: left;
  }

  .description {
    max-width: 25rem;
    float: right;
    margin-bottom: 2rem;
  }

  .product {
    font-size: x-large;
    font-weight: 400;
  }

  .product ~ * {
    font-size: small;
  }

  .stock {
    margin-block: 0rem;
    font-size: x-small;
  }

  .flex {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .column {
    flex-direction: column;
    align-items: start;
  }

  .button__text {
    padding: 10px 16px;
    font-weight: 400;
    font-size: 14px;
    letter-spacing: 0.75px;
    text-transform: uppercase;
    border-radius: 48px;
  }

  .state-link__text {
    background: #3f51b5;
    color: beige;
    border: none;
  }
</style>
