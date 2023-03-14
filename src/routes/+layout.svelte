<header>
  <div>
    <h2 class="title opacity">SOON_</h2>
    <h2 class="page">Basket App</h2>
  </div>
  <div>
    <a href="/">
      <img class="basket" src="shopping-basket.png" alt="basket" />
    </a>
    <button class="button__icon state-disabled"> 0 </button>
  </div>
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

  .button__icon {
    border-radius: 24px;
    font-size: small;
    width: 2rem;
    height: 2rem;
    color: beige;
    scale: 0.8;
  }

  .state-disabled {
    border: none;
    background: rgba(0, 0, 0, 0.25);
  }
</style>
