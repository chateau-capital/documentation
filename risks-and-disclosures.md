# ⚠️ Risks & Disclosures

At Chateau, transparency is a foundational principle. While **chUSD** is designed to provide stable, on-chain capital for private market participation, it’s important to understand the risks inherent in holding a **RWA-backed stablecoin**. Below are the key risk categories, along with how we address them and the broader considerations for users and institutions.

***

#### 🧾 Risk of Synthetic Dollar Exposure

**chUSD** is a synthetic dollar instrument — it maintains a peg through collateralized backing and issuance mechanics, but it is not legal tender, nor is it a claim on fiat USD. It behaves like a dollar on-chain, but price stability depends on market liquidity, trust in the structure, and redemption mechanisms.

***

#### 🏦 Custodial & Collateral Risk

chUSD may be partially or fully backed by assets held in regulated custodial accounts or smart-contract-controlled vaults. This introduces two layers of risk:

* **Custodian exposure**: Assets held at banks or custodians may be subject to seizure, censorship, or failure (e.g., SVB-type events).
* **Collateral performance**: If underlying assets (e.g. private credit portfolios) underperform or become illiquid, it may impair redemption confidence.

***

#### 🔄 Exchange & Liquidity Risk

chUSD depends on secondary markets and liquidity partners for convertibility. In the event of exchange downtime, smart contract failure, or pool imbalances, users may experience slippage, redemption delays, or temporarily impaired peg performance.

***

#### 💰 Funding & Liquidation Risk

In tokenized credit structures where chUSD may be used as a funding or staking mechanism, there is a risk of **capital inefficiency** or **collateral mismatch** — particularly during market stress, redemptions, or portfolio underperformance. Chateau actively manages thresholds and asset coverage ratios but cannot eliminate systemic risk.

***

#### 🧩 Structural Risk of chUSD as a RWA Stablecoin

Like other asset-backed stablecoins (USDC, USDT, etc.), chUSD faces risks tied to its integration with **real-world assets (RWAs)** and TradFi infrastructure:

* **Custodial concentration**: Assets are ultimately held within traditional financial institutions, subject to regulation, surveillance, or blacklisting.
* **Return-free risk**: Users earn no yield from the yield-bearing collateral; they carry peg and counterparty risk while issuers (or upstream structures) capture income.
* **Unsecured exposure**: Users effectively hold a synthetic credit position to both Chateau and the entities holding/issuing collateral, even when the structure is bankruptcy-remote.

***

#### ⚠️ RWA & Regulatory Considerations

As a stablecoin partially or fully collateralized by real-world instruments, **chUSD is inherently exposed to:**

* Regulatory actions targeting stablecoin issuance or redemption mechanisms
* Jurisdictional risk across banking, custody, and fund servicing partners
* Potential conflicts between on-chain asset logic and off-chain enforcement

***

### 🧭 Risk Management Practices

* All collateral positions are tracked and reported transparently
* Chateau uses institutional custodians and independent legal structuring
* We publish on-chain proof of assets, audit trails, and risk parameters when available
* Redemption policies are structured with thresholds and liquidity buffers
* Chateau may introduce yield-sharing models to better align risk and return
