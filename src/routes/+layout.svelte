<script>
  import Item from "./basket/Item.svelte";
  import countStore from "../store";
</script>

<header>
  <div>
    <h1 class="title opacity">SOON_</h1>
    <h1>Basket App</h1>
  </div>
  <aside>
    <a href="/basket">
      <img
        class="basket"
        style="margin-right: 3rem"
        src="shopping-basket.png"
        alt="basket"
      />
    </a>
    <span
      class="button__icon--count {$countStore > 0
        ? 'state-link__text'
        : 'state-disabled'}"
    >
      {$countStore}
    </span>
  </aside>
</header>
<hr class="opacity" />

<slot />

<style>
  :global(*) {
    font-family: "Roboto", sans-serif;
    font-style: normal;
    font-weight: 300;
    line-height: 28px;
  }

  :global(.page) {
    margin: 2.5rem;
  }

  .title {
    margin-inline: 0.5em;
  }

  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 2rem;
    margin-bottom: 0%;
  }

  div {
    display: flex;
    align-items: center;
  }

  hr {
    margin: 2.5rem;
    margin-top: 0%;
  }

  :global(.opacity) {
    opacity: 0.4;
  }

  .basket {
    margin-right: 0.5rem;
    width: 1.5rem;
    height: 1.5rem;
  }

  .button__icon--count {
    border-radius: 24px;
    font-size: small;
    width: 2rem;
    height: 2rem;
    color: inherit;
    scale: 0.8;

    position: absolute;
    top: 3rem;
    right: 3rem;
  }

  .state-disabled {
    border: none;
    background: rgba(0, 0, 0, 0.25);
  }
</style>
