---
description: Risk free arbitrage
---

# ⚖️ Peg Stability & Arbitrage Mechanism

**chUSD** is designed to maintain a soft peg to the U.S. dollar, supported by real-world asset (RWA) collateral and on-chain mint/redeem mechanisms. To incentivize price stability across markets, chUSD supports cross-market arbitrage by allowing approved participants to profit from short-term price dislocations.



<figure><img src=".gitbook/assets/ChatGPT Image Jun 13, 2025 at 01_00_55 AM.png" alt="" width="375"><figcaption></figcaption></figure>

***

#### 🔁 Cross-Market Arbitrage

When the secondary market price of **chUSD** diverges from its target peg (i.e. $1.00), whitelisted users can execute arbitrage via the **mint & redeem contracts**.

This helps anchor the peg and ensures that chUSD trades closely in line with its backing value.

**Example A – chUSD trades below peg:**

* Buy chUSD on Curve or Uniswap for $0.95
* Redeem chUSD via Chateau for $1.00 worth of backing assets
* Realize a $0.05 profit per token

**Example B – chUSD trades above peg:**

* Mint chUSD from Chateau at $1.00 using stablecoins (e.g., USDC)
* Sell chUSD on a DEX or CEX for $1.03
* Capture the spread as profit

***

#### 🛠️ Trade Access & Infrastructure

* Only **whitelisted participants** may directly access the mint/redeem contracts
* chUSD is **backed by RWAs**, with a portion of reserves held in on-chain stablecoins to enable real-time redemption
* Redemption liquidity is replenished systematically from Chateau’s treasury, which maintains a buffer (e.g. 4% of assets) in stable, liquid form across qualified custodians

***

#### 🧮 What Holds the Peg

* **Asset-backed stability**: chUSD is backed by private credit and tokenized SPVs, not algorithmic mechanisms
* **Smart contract-based arbitrage**: ensures that dislocations can be traded away when spreads appear
* **Minimal correlation to volatile crypto assets**: since underlying value is tied to off-chain yield, short-term volatility on DEXes doesn’t impair long-term peg confidence
