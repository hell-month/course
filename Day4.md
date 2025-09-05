---
marp: true
---

# Day 4

Additional features to CPAMM

---

## So far..

- Add liquidity
- Swap based on the CPAMM Formula $x \times y = k$

---

## But that's not all!

- LP Token
- Remove liquidity
- Fees
- Systematic way to deploy and manage each pair

---

## LP token

Example: 
- Alice adds 10 ETH and 1000 DAI to the pool.
- Bob adds 1 ETH and 100 DAI to the pool.

Problem: 
How to keep track of each liquidity provider (LP)'s share of the pool?

---

## LP token (cont.)

Solution:
Mint LP tokens to LPs when they add liquidity.

Problem:
But how much LP Token to mint?

---

## LP token (cont.)

Equations:
- First time (geometric mean): $LP_{to\ mint} = \sqrt{x_{deposited} \times y_{deposited}}$
- Not first time (ratio): $LP_{to\ mint} = \frac{x_{deposited}}{x_{existing}} \times LP_{existing}$

Example:
- First time: Alice adds 10 ETH and 1000 DAI to the pool. She gets $\sqrt{10 \times 1000} = \sqrt{10000} = 100$ LP tokens.
- Second time: Bob adds 1 ETH and 100 DAI to the pool. He gets $\frac{1}{10} \times 100 = 10$ LP tokens. Even if we use DAI side, we get the same result: $\frac{100}{1000} \times 100 = 10$ LP tokens.

---
<style scoped>
section {
  font-size: 22px;
}
</style>

## Removing liquidity

When a LP wants to remove their liquidity, they will 'burn' their LP tokens to receive their share of the underlying assets.

Bob wants to remove all of his liquidity.
- $LP_{total} = 110$
- $LP_{Bob} = 10$

Equation:
- $x_{to\ withdraw} = \frac{LP_{Bob}}{LP_{total}} \times x_{existing}$
- $y_{to\ withdraw} = \frac{LP_{Bob}}{LP_{total}} \times y_{existing}$

Example:
- $x_{to\ withdraw} = \frac{10}{110} \times 11 = 1$ ETH
- $y_{to\ withdraw} = \frac{10}{110} \times 1100 = 100$ DAI
- $LP_{Bob}$ is burned, so $LP_{total}$ is now 100.

---

## Fees

1. Protocol fee: optional 0.5% fee that goes to a `feeTo` address.
    0.5% of the LP token to be minted is minted to `feeTo` address (usually controlled by the protocol).

1. Swap fee: 0.3% of the swap amount goes to the liquidity pool.
    Collected every swap, which increases the value of LP tokens.

---

## Fees (cont.)

Recall the [Day 1](./Day1.md) CPAMM formula

Swap fee changes the CPAMM formula slightly:
- Old formula: $(x + \Delta x) \times (y - \Delta y) = k$
- New formula: $(x + 0.997 \times \Delta x) \times (y - \Delta y) = k$

---

## Fees (cont.)

Recall this example on [Day 1](./Day1.md):
$x = \text{Amount of USDC}$
$y = \text{Amount of BTC}$

Let $x = 1000$ and $y = 1$. Then $k = 1 \times 1000$
Alice wants to pay 1000 USDC to get BTC. How much BTC can she get?

New formula: $(x + 0.997 \times \Delta x) \times (y - \Delta y) = k$

$(1000 + 0.997 \times 1000) \times (1 - \Delta y) = 1000$
$1997 \times (1 - \Delta y) = 1000$
$1 - \Delta y = \frac{1000}{1997}$
$-\Delta y = \frac{1000}{1997} - 1$
$\therefore \Delta y = 1 - \frac{1000}{1997} = \frac{997}{1997} \approx 0.49925$ BTC (not 0.5 BTC anymore)

---

## Factory contract

Problem: need to manage multiple pairs of tokens.
USDC-ETH, DAI-ETH, USDT-ETH, USDC-DAI, ...

Solution: 'factory' contract
- Store information about all pairs
- Create new pairs

---

# AI Guiding questions
<style scoped>
section {
  font-size: 21px;
}
</style>
Ask ChatGPT these questions yourself to kickstart your own study (feel free to tweak these questions and ask follow-up questions):

> Why is the geometric mean used to calculate the initial liquidity provider (LP) tokens in a constant product automated market maker (CPAMM) like Uniswap V2?

> Why does it make sense to use the ratio of one deposited asset to the existing amount of that asset to calculate LP tokens for subsequent liquidity providers in a CPAMM, and not the other asset or both?

> What is the role of an LP token, why is it needed, and how can it be used?

> Explain the concept of a factory pattern in programming and how it applies to the deployment of multiple token pairs in a decentralized exchange like Uniswap.

---

# Assignment 2

1. Make **another branch** from your latest work on Assignment 1A & 1B, called **`assignment-2`**
2. Merge or rebase the latest changes from https://github.com/hell-month/cohort-1-assignments-public/ onto `assignment-2` branch.
3. Keep using `assignment-2` branch for `assignment-2` Push the latest changes to this branch. **DO NOT use the `main` branch for this assignment.**

---
<style scoped>
section {
  font-size: 21px;
}
</style>

# Assignment 2 (cont.)

This assignment is about adding more features to Assignment 1A under `2` folder. Implement:
- LP Token
- Remove liquidity
- Fees
- Factory contract

All forge tests must be passing.

Submit `MiniAMM` and `MiniAMMFactory` deployment address on Flare Coston2 network on the **Assignment 2 tab** on https://docs.google.com/spreadsheets/d/1LtR6zEHqmUgXdRn0NSkm2pmDreL8w3GBOMDGs7vVUGE/edit?gid=880577982#gid=880577982

Deadline: 23:59 KST, Sept 15 (Mon)
