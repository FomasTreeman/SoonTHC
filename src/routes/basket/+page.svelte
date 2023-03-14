<script>
  //   let products = {
  //     product: "Waxed Cotton Hooded Jacket",
  //     img: "clothing.png",
  //     price: 650,
  //     quantity: 3,
  //   };
  let price = [650.0];
  let quantity = [1];
  let total = [650.0];
  let subtotal = 650;

  function addQuantity() {
    quantity[0] === 10 ? false : (quantity[0] += 1);
    setTotal();
    setSubtotal();
  }

  function minusQuantity() {
    quantity[0] != 1 ? (quantity[0] -= 1) : false;
    setTotal();
    setSubtotal();
  }

  function setTotal() {
    total[0] = quantity[0] * price[0];
  }

  function setSubtotal() {
    subtotal = total.reduce((acc, curr) => acc + curr);
  }
</script>

<div class="page">
  <main class="flex">
    <section>
      <p class="opacity">PRODUCT</p>
      <div class="flex ">
        <a href="/">Waxed Cotton Hooded Jacket</a>
        <img src="clothing.png" alt="red jacket" />
      </div>
    </section>
    <section>
      <p class="opacity">PRICE</p>
      <p>£650</p>
    </section>
    <section>
      <p class="opacity">QUANTITY</p>
      <section class="flex flex__align-center" style="width: 7rem;">
        <button class="button__icon state-link__icon" on:click={minusQuantity}>
          -
        </button>
        <p>{quantity}</p>
        <button class="button__icon state-link__icon" on:click={addQuantity}>
          +
        </button>
      </section>
    </section>
    <section>
      <p class="opacity">TOTAL</p>
      <p>£{total}</p>
    </section>
  </main>
  <hr class="opacity" />
  <article class="checkout">
    <h3 class="opacity" style="margin: 0px">SUBTOTAL</h3>
    <p>£{subtotal}</p>
    <button class="button__text state-link__text" style="margin-block: 2rem">
      GO TO CHECKOUT
    </button>
  </article>
</div>

<style>
  main img {
    width: 8rem;
    margin: 1rem 1rem 1rem 4rem;
    /* margin-left: 4rem; */
    /* margin-right: 1rem; */
  }

  main :first-child a {
    text-decoration: none;
    color: inherit;
  }

  hr {
    margin-block: 3rem;
  }

  .flex {
    display: flex;
    align-items: start;
  }

  main.flex {
    gap: 4rem;
  }

  main.flex > :nth-child(2) {
    margin-left: auto;
  }

  main.flex > :last-child {
    width: 10rem;
  }

  .flex__align-center {
    align-items: center;
    justify-content: space-between;
  }

  .opacity {
    font-size: x-small;
  }

  .opacity + p {
    margin: 0px;
  }

  .checkout {
    float: right;
    margin-top: 3rem;
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
