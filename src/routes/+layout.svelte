<script>
  import countStore from "../store";
</script>

<header>
  <h1 class="title opacity">SOON_</h1>
  <h1>Basket App</h1>
  <a href="/basket">
    <img src="shopping-basket.png" alt="basket" />
  </a>
  <p class="button_icon {$countStore > 0 ? 'state-full' : 'state-empty'}">
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
    margin-inline: 0.5rem;
    display: inline-block;
    line-height: 0px;
  }

  p {
    margin-block: auto;
    text-align: center;
    line-height: 32px;
  }

  img {
    margin-right: 0.5rem;
    width: 1.5rem;
    height: 1.5rem;
  }

  hr {
    margin: 2.5rem;
    margin-top: 0%;
  }

  .button_icon {
    border-radius: 24px;
    font-size: small;
    width: 2rem;
    height: 2rem;
    color: inherit;
    scale: 0.8;
  }

  .state-full {
    background: #3f51b5;
    color: beige;
    border: none;
  }

  .state-empty {
    border: none;
    background: rgba(0, 0, 0, 0.25);
  }
</style>
