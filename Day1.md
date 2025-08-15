---
marp: true
---

# Day 1

---

# Problem

![bg right](orderbook.png)

Orderbooks are boring & inefficient

Any ways to trade other than orderbooks?

---

# Intuition

Consider BTC/KRW pair

Simplify actions into:

1. buy
2. sell

When

1. buy: price ⬆
2. sell: price ⬇️

Can we make this just happen without an orderbook?

---

# [Uniswap](https://app.uniswap.org): yes

![height:13cm](uniswap-interface.png)

---

# [Brief history of Uniswap](https://blog.uniswap.org/uniswap-history)

1. V1: Proof of concept
2. **V2: Constant Product (x \* y = k) Automated Market Maker**
3. V3: Concentrated liquidity & Capital efficiency
4. V4: V3 + hooks

---

# Constant Product Automated Market Maker (CPAMM)

$x \times y = k$

where

$x$ is the amount of token A
$y$ is the amount of token B
$k$ is the product of $x$ and $y$

---

# AI Guiding questions

Ask ChatGPT these questions yourself to kickstart your research (feel free to tweak these questions):

> What's the difference between trading on orderbook and constant product automated market maker?

> Let's talk about constant product automated market maker based on x \* y = k. Say the market initializes with 1 BTC and 1000 USDC. Then tell me the k, and give me an example of how would a trade affect the price of BTC relative to USDC.

> On Uniswap v2, does k actually stay constant all the time? Or are there conditions on which it changes? Why?

---

# Recommended reading list

- [Uniswap V1 Whitepaper](https://raw.githubusercontent.com/hell-month/static/master/uniswap%20v1%20whitepaper%20hackmd.pdf)
- [Uniswap V2 Core whitepaper](https://app.uniswap.org/whitepaper.pdf) (you can choose to read only these parts below)
  ```
  1. Introduction
  2.1 ERC-20 pairs
  3. Other changes
  ```
- Page 1-3 of [Formal Specification of Constant Product (x × y = k) Market Maker Model and Implementation](https://raw.githubusercontent.com/runtimeverification/verified-smart-contracts/master/uniswap/x-y-k.pdf)
- [On Path Independence](https://vitalik.eth.limo/general/2017/06/22/marketmakers.html) by Vitalik
- [Let's run on-chain decentralized exchanges the way we run prediction markets](https://www.reddit.com/r/ethereum/comments/55m04x/lets_run_onchain_decentralized_exchanges_the_way/) by Vitalik
- [Improving front running resistance of x\*y=k market makers](https://ethresear.ch/t/improving-front-running-resistance-of-x-y-k-market-makers/1281) by [Vitalik](https://ethresear.ch/u/vbuterin)

---

# Assignment 1A: write and deploy your first x \* y = k contract

---

# Assignment 1B (optional): bootstrap your first local development environment

Here's the detailed requirement of your local development environment.

- Run all containers on docker-compose
- Access Blockscout on localhost
- Access Geth on localhost
- Access deployed smart contracts from Assignment 1

---

# Submission
