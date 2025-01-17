<script>
  import Coin from './Coin.svelte';

  let numOfCoins = $state(0);

  function handleNumOfCoins() {
    numOfCoins += 2;
  }
</script>

<div class="wrapper">
  <main>
    <Coin handleNumOfCoins={handleNumOfCoins} />
  </main>
  <footer>
    Your coin balance:
    <strong>{numOfCoins}</strong>
  </footer>
</div>