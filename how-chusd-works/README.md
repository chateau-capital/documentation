---
description: chUSD 101
---

# How chUSD works

**Chateau USD (“chUSD”)** is a synthetic U.S. dollar, fully backed by on-chain collateral and private credit yields. Built on a fork of **Ethena’s USDe** codebase with minimal modifications, chUSD combines onchain transparency with institutional credit exposure. We extend our appreciation to our partners at [Ethena.fi](https://ethena.fi/) for open-sourcing their architecture.

Initially collateralized by **USDC** and **USDT**, chUSD will expand to include additional asset types over time.\
\
Through **Chateau Protocol**, holders can stake chUSD into **schUSD**, a yield-accruing instrument powered by **Covenant VC’s** private credit strategies. Covenant VC, a New York–based hedge fund, manages a $500M institutional credit portfolio delivering consistently high-Sharpe returns.

Chateau’s long-term objective is to broaden access to real-world asset (RWA) vaults, providing investors with diversified, institutional-grade opportunities across private markets. For further insight into the private credit landscape, refer to the _Private Credit Overview_ section.

***

### Peg Stability Mechanism

chUSD maintains its USD peg through active collateral management.

Chateau employs **no material leverage**. chUSD is held at qualified institutional custodians. Mint and Redeem operations are real time, enabling free market arbitrage if chUSD breaks peg.

***

#### Key Functions

1. **Acquire chUSD:** Permissionless access via external DEX liquidity pools using USDC or USDT.
2. **Mint chUSD:** Whitelisted institutional participants may mint chUSD directly by transferring accepted reserve assets, subject to KYC/KYB clearance.
3. **Redeem chUSD:** Authorized parties can redeem chUSD for the corresponding backing assets under the same compliance conditions.
4. **Stake chUSD:** Eligible users can stake into **schUSD** to receive rewards from protocol revenue streams.

***

### Yield Generation

The Chateau Protocol generates sustainable yield through three primary sources:

1. **Private Credit Returns** — derived from Covenant VC’s professionally managed, collateralized lending portfolio.
2. **Stable and Staked Asset Rewards** — interest or staking income from collateral held on-chain.

Returns are variable and denominated in the underlying assets.\
If sustained negative funding conditions arise, Chateau’s reserve fund absorbs any shortfall, ensuring peg and stability continuity.

***

### Risk Management Practices 🧭

Chateau applies institutional-grade oversight and transparent reporting across all layers of its architecture:

* **Transparent Collateral Tracking:** All positions are monitored through **Pyth** oracles, providing real-time, on-chain proof of assets and audit trails.
* **Active Transaction Monitoring:** The **GATEKEEPER\_ROLE** oversees protocol activity and can revoke **MINTER\_ROLE** privileges upon detection of irregular transactions.
* **Institutional Custody:** Assets are held with **BitGo** and other regulated custodians under independent legal structuring.
* **Redemption Safeguards:** Redemption processes are governed by liquidity buffers and redemption thresholds to ensure orderly market operations.

***

### Risk Factors

chUSD is exposed to general on-chain and market risks, including:

1. Smart contract and oracle risk
2. Counterparty or custodian exposure
3. Market and liquidity volatility
4. External platform and operational risk

Mitigation measures include diversification across custodians, and hedging counterparties, as well as continuous transaction monitoring and collateral transparency.

***

**Every element of Chateau’s system is engineered for capital integrity, transparency, and scalability — bridging institutional credit yields with on-chain stability.**
