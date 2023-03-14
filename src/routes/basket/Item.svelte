<script>
  export let product;
  export let setSubtotal;

  function addQuantity() {
    product.quantity === 10 ? false : (product.quantity += 1);
    // setTotal(index);
    setSubtotal();
  }

  function minusQuantity() {
    product.quantity != 1 ? (product.quantity -= 1) : false;
    // setTotal();
    setSubtotal();
  }
</script>

<main class="flex">
  <a href="/">{product.product}</a>
  <a href="/">
    <img src={product.img} alt="red jacket" />
  </a>
  <section>
    <p>£{product.price}</p>
  </section>
  <section>
    <div class="flex flex__align-center" style="width: 7rem;">
      <button class="button__icon state-link__icon" on:click={minusQuantity}>
        -
      </button>
      <p>{product.quantity}</p>
      <button class="button__icon state-link__icon" on:click={addQuantity}>
        +
      </button>
    </div>
  </section>
  <section>
    <p>£{product.total()}</p>
  </section>
</main>

<!-- <hr class="opacity" /> -->
<style>
  main {
    margin-block: 2rem;
  }

  main img {
    height: 7rem;
    max-width: 9rem;
    margin: 1rem;
    /* margin-right: auto; */
  }

  main a {
    text-decoration: none;
    color: inherit;
  }

  .flex {
    display: flex;
    align-items: start;
    justify-content: end;
  }
  /* 
  .space-between {
    justify-content: space-between;
  } */

  main.flex {
    gap: 4rem;
  }

  main.flex > :first-child {
    margin-right: auto;
  }

  main.flex > :nth-last-child(3) {
    width: 3rem;
    text-align: start;
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
