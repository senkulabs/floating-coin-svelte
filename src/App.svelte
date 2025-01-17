<script>
  import Coin from './Coin.svelte';
  import FloatingText from './FloatingText.svelte';

  const CHOCOLATE_COST = 9;

  let numOfCoins = $state(0);
  let numOfChocolates = $state(0);
  let floatingTextKey = $state('initial');

  function buyChocolate() {
    numOfCoins = numOfCoins - CHOCOLATE_COST;
    numOfChocolates = numOfChocolates + 1;
  }

  function handleNumOfCoins() {
    numOfCoins += 2;
    floatingTextKey = crypto.randomUUID();
  }
</script>

<div class="wrapper">
  <main>
    <Coin handleNumOfCoins={handleNumOfCoins} />
    {#if floatingTextKey !== 'initial'}
    <div class="floatingNumWrapper">
      {#key floatingTextKey}
      <FloatingText>
        +2
      </FloatingText>
      {/key}
    </div>
    {/if}
    <button disabled={numOfCoins < CHOCOLATE_COST} class="shop-item" onclick={buyChocolate}>
      Buy chocolate {numOfChocolates > 0 ? (`(${numOfChocolates})`) : ''}
    </button>
  </main>
  <footer>
    Your coin balance:
    <strong>{numOfCoins}</strong>
  </footer>
</div>

<style>
.wrapper {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 48px;
}

.wrapper main {
  position: relative;
  display: grid;
  place-content: center;
}

.wrapper footer {
  padding: 16px;
  font-size: 1.25rem;
  font-weight: 400;
  text-align: center;
}

.wrapper footer strong {
  display: block;
  font-size: 2rem;
}

.floatingNumWrapper {
  position: absolute;
  top: -48px;
  right: 0;
  padding: 32px;
  font-size: 3rem;
  font-weight: bold;
  color: gold;
  pointer-events: none;
  user-select: none;
}
</style>