<script>
    let { handleNumOfCoins } = $props();
</script>

<div class="coin-wrapper">
    <button class="coin" onclick={handleNumOfCoins}>
        <span class="visually-hidden">Add 2 coin</span>
        <img class="coin-image" alt="" src="https://sandpack-bundler.vercel.app/img/toonie.png" />
    </button>
</div>

<style>
.coin {
    display: block;
    background: transparent;
    border: none;
    width: 200px;
    cursor: pointer;
    transition: transform 500ms;
    will-change: transform;
}

.coin:hover {
    transform: scale(1.05);
    transition: transform 200ms;
}

.coin:active {
    transform: scale(0.95);
    transition: transform 0ms;
}

.coin-image {
    display: block;
    width: 100%;
    user-select: none;
}
</style>