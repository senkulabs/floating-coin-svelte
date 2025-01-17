<script>
    let { children } = $props();
</script>

<div class="wrapper">
    {@render children()}
</div>

<style>
@keyframes floatBy {
    0% {
        transform: translateY(50%);
        opacity: 0;
    }
    80% {
        opacity: 1;
    }
    100% {
        transform: translateY(-50%);
        opacity: 0;
    }
}

.wrapper {
    animation: floatBy 600ms both cubic-bezier(0,.66,.48,1);
}
</style>