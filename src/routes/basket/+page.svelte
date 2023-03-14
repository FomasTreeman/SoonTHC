<script>
  import Item from "./Item.svelte";
  import countStore from "../../store";

  let subtotal;
  let products = [
    {
      product: "Waxed Cotton Hooded Jacket",
      img: "clothing.png",
      price: 650,
      quantity: 3,
      total: function () {
        return this.price * this.quantity;
      },
    },
    {
      product: "Another Amazing Jacket",
      img: "another.png",
      price: 1000,
      quantity: 9,
      total: function () {
        return this.price * this.quantity;
      },
    },
    {
      product: "Jacket",
      img: "top.png",
      price: 60,
      quantity: 2,
      total: function () {
        return this.price * this.quantity;
      },
    },
  ];

  function setSubtotal() {
    subtotal = products.reduce((acc, curr) => {
      return acc + curr.total();
    }, 0);
    // console.log(subtotal);
  }

  function getSubtotal() {
    return products.reduce((acc, curr) => {
      return acc + curr.total();
    }, 0);
  }

  setSubtotal();

  function getBasketCount() {
    const count = products.reduce((acc, curr) => acc + curr.quantity, 0);
    console.log(count);
    return count;
  }

  $: {
    countStore.set(products.reduce((acc, curr) => acc + curr.quantity, 0));
    subtotal = products.reduce((acc, curr) => {
      return acc + curr.total();
    }, 0);
  }
</script>

<div class="page">
  <nav class="flex">
    <p class="opacity">PRODUCT</p>
    <p class="opacity">PRICE</p>
    <p class="opacity">QUANTITY</p>
    <p class="opacity">TOTAL</p>
  </nav>
  {#each products as product}
    <Item bind:product />
  {/each}
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
  nav.flex {
    gap: 4rem;
  }

  nav.flex > :first-child {
    margin-right: auto;
  }

  nav.flex > :nth-child(2) {
    width: 3rem;
  }

  nav.flex > :nth-child(3) {
    width: 7rem;
  }

  nav.flex > :last-child {
    width: 10rem;
  }

  hr {
    margin-block: 3rem;
  }

  .flex {
    display: flex;
    align-items: start;
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
