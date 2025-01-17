# Floating Coin in Svelte

Floating Coin in Svelte build with Vite + Svelte. This code is a porting of [Floating Coin in React](https://github.com/senkulabs/floating-coin-react).

## Current Issue

When we buy a chocolate, the animation of "+2" trigger. What we expect is the animation doesn't trigger when we buy the chocolate. Here's the acceptance criteria:

- Buying a chocolate shouldn't re-trigger the "+2" animation
  - Chocolate cost 9 coins, so test this, you need to click the coin 5 times, and then click the "Buy chocolate"
- Clicking the coin should still show the "+2" animation
- The "+2" animation should still not be shown when the page first loads

## How to run?

```sh
pnpm install
pnpm run dev
```