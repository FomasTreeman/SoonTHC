<script>
  import QuantityInput from "../../lib/QuantityInput.svelte";
  export let product;
</script>

<section class="flex">
  <a href="/">{product.product}</a>
  <a href="/">
    <img src={product.img} alt="red jacket" />
  </a>
  <p>£{product.price}</p>
  <QuantityInput maxQuantity={10} bind:quantity={product.quantity} />
  <p>£{product.price * product.quantity}</p>
</section>

<!-- <hr class="opacity" /> -->
<style>
  section {
    margin-block: 2rem;
  }

  img {
    height: 7rem;
    max-width: 9rem;
    margin: 1rem;
  }

  /* accesibilty note - not obvious its a link */
  a {
    text-decoration: none;
    color: inherit;
  }

  .flex {
    display: flex;
    align-items: start;
    justify-content: end;
  }

  .flex {
    gap: 4rem;
  }

  .flex > :first-child {
    margin-right: auto;
  }

  .flex > :nth-last-child(3) {
    width: 3rem;
    text-align: start;
  }

  .flex > :last-child {
    width: 10rem;
  }
</style>
