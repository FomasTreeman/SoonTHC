<script>
  let stock = 10;
  let quantity = 1;
  let basketCount = 0;

  function addQuantity() {
    quantity === stock ? false : (quantity += 1);
  }

  function minusQuantity() {
    quantity != 1 ? (quantity -= 1) : false;
  }

  function setBasketCount() {
    basketCount += quantity;
  }
</script>

<button
  class="button__icon--count {basketCount > 0
    ? 'state-link__text'
    : 'state-disabled'}"
>
  {basketCount}
</button>
<img class="item" src="clothing.png" alt="item of clothing" />
<section class="flex column">
  <article class="description">
    <h3 class="product">Waxed Cotton Hooded Jacket</h3>
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
  <section class="flex" style="width: 7rem;">
    <button class="button__icon state-link__icon" on:click={minusQuantity}>
      -
    </button>
    <p>{quantity}</p>
    <button class="button__icon state-link__icon" on:click={addQuantity}>
      +
    </button>
  </section>
  <button
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

  .button__icon {
    border-radius: 24px;
    font-size: medium;
    font-weight: 300;
    width: 2rem;
    height: 2rem;
  }

  .button__icon--count {
    border-radius: 24px;
    font-size: small;
    width: 2rem;
    height: 2rem;
    color: beige;
    scale: 0.8;

    position: absolute;
    top: 3rem;
    right: 3rem;
  }

  .state-disabled {
    border: none;
    background: rgba(0, 0, 0, 0.25);
  }
  .state-link__icon {
    background-color: transparent;
    color: #3f51b5;
    border: 1px solid #3f51b5;
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
