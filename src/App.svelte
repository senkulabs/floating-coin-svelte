<script>
  import './Coin.css';

  let numOfCoins = $state(0);
</script>

<div class="wrapper">
  <main>
    <div class="coin-wrapper">
      <button class="coin" onclick={() => numOfCoins += 2}>
        <span class="visually-hidden">Add 2 coin</span>
        <img class="coin-image" alt="" src="https://sandpack-bundler.vercel.app/img/toonie.png" />
      </button>
    </div>
  </main>
  <footer>
    Your coin balance:
    <strong>{numOfCoins}</strong>
  </footer>
</div>