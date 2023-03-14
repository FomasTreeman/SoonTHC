<script>
  import Item from "./basket/Item.svelte";
  import countStore from "../store";
</script>

<header>
  <h1 class="title opacity">SOON_</h1>
  <h1>Basket App</h1>
  <a href="/basket">
    <img class="basket" src="shopping-basket.png" alt="basket" />
  </a>
  <p
    class="button__icon--count {$countStore > 0
      ? 'state-link__text'
      : 'state-disabled'}"
  >
    {$countStore}
  </p>
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

  :global(.opacity) {
    opacity: 0.4;
  }

  .title {
    margin-inline: 0.5em;
  }

  header {
    display: flex;
    align-items: baseline;
    margin: 2rem;
    margin-bottom: 0%;
  }

  header > :nth-child(2) {
    flex-grow: 1;
  }

  a,
  p {
    display: inline-block;
    line-height: 0px;
    margin-inline: 0.5rem;
  }

  header > :last-child {
    margin-block: auto;
    text-align: center;
    line-height: 32px;
  }

  hr {
    margin: 2.5rem;
    margin-top: 0%;
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
  }

  .state-link__text {
    background: #3f51b5;
    color: beige;
    border: none;
  }

  .state-disabled {
    border: none;
    background: rgba(0, 0, 0, 0.25);
  }
</style>
