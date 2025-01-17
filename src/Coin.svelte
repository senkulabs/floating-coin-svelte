<script>
    import './Coin.css';
    let { handleNumOfCoins } = $props();
</script>

<div class="coin-wrapper">
    <button class="coin" onclick={handleNumOfCoins}>
        <span class="visually-hidden">Add 2 coin</span>
        <img class="coin-image" alt="" src="https://sandpack-bundler.vercel.app/img/toonie.png" />
    </button>
</div>