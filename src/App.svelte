<script>
  import Coin from './Coin.svelte';
  import FloatingText from './FloatingText.svelte';

  let numOfCoins = $state(0);

  function handleNumOfCoins() {
    numOfCoins += 2;
  }
</script>

<div class="wrapper">
  <main>
    <Coin handleNumOfCoins={handleNumOfCoins} />
    {#if numOfCoins > 0}
    <div class="floatingNumWrapper">
      {#key numOfCoins}
      <FloatingText>
        +2
      </FloatingText>
      {/key}
    </div>
    {/if}
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