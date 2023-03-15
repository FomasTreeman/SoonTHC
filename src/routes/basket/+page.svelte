<script>
  import Item from "./Item.svelte";
  import countStore from "../../store";

  let subtotal;
  let basket = [
    {
      product: "Waxed Cotton Hooded Jacket",
      img: "clothing.png",
      price: 650,
      quantity: 3,
    },
    {
      product: "Another Amazing Jacket",
      img: "another.png",
      price: 1000,
      quantity: 9,
    },
    {
      product: "Jacket",
      img: "top.png",
      price: 60,
      quantity: 2,
    },
  ];

  function getSubtotal() {
    return basket.reduce((acc, curr) => acc + curr.price * curr.quantity, 0);
  }

  subtotal = getSubtotal();

  $: {
    countStore.set(basket.reduce((acc, curr) => acc + curr.quantity, 0));
    subtotal = getSubtotal();
  }
</script>

<main class="page">
  <nav>
    <p class="opacity">PRODUCT</p>
    <p class="opacity">PRICE</p>
    <p class="opacity">QUANTITY</p>
    <p class="opacity">TOTAL</p>
  </nav>
  {#each basket as product}
    <Item bind:product />
  {/each}
  <hr class="opacity" />

  <article>
    <h3 class="opacity" style="margin: 0px">SUBTOTAL</h3>
    <p>£{subtotal}</p>
    <button> GO TO CHECKOUT </button>
  </article>
</main>

<style>
  nav {
    display: flex;
    align-items: start;
    gap: 4rem;
  }

  nav > :first-child {
    margin-right: auto;
  }

  nav > :nth-child(2) {
    width: 3rem;
  }

  nav > :nth-child(3) {
    width: 7rem;
  }

  nav > :last-child {
    width: 10rem;
  }

  button {
    margin-block: 2rem;
    padding: 10px 16px;
    font-weight: 400;
    font-size: 14px;
    letter-spacing: 0.75px;
    background: #3f51b5;
    color: beige;
    border: none;
    border-radius: 48px;
    text-transform: uppercase;
  }

  hr {
    margin-block: 3rem;
  }

  article {
    float: right;
    margin-top: 3rem;
  }

  .opacity {
    font-size: x-small;
  }

  .opacity + p {
    margin: 0px;
  }
</style>
