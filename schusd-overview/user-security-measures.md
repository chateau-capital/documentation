# User Security Measures

## Security and Governance Overview

**Chateau Protocol** employs a layered security framework to ensure the integrity, resilience, and transparency of all deployed smart contracts.\
These measures are designed primarily to safeguard **protocol assets** and **investor capital**, while also maintaining reasonable, auditable, and decentralized governance standards.

The following list outlines some — though not all — of the key security and governance mechanisms implemented across **chUSD** and **schUSD** contracts.

***

### Security Measures

#### 🧱 **Battle-Tested Foundations**

All Chateau vaults inherit from **OpenZeppelin’s ERC-4626 Token Vault** implementation — the most widely audited and deployed standard for on-chain yield instruments.\
This provides high assurance that Chateau’s contracts are built on thoroughly reviewed, community-validated code.

***

#### 🕒 **Unstake Cooldown Period**

When a user unstakes **schUSD**, it is immediately settled back into **chUSD** within the smart contract.\
However, the resulting chUSD cannot be withdrawn until a **cooldown period** has elapsed.\
This design prevents rapid in-block withdrawal exploits and front-running during market or reward events.

* The cooldown duration is set by governance, up to a **maximum of 90 days**.
* This feature provides operational flexibility while ensuring liquidity management remains stable under stress conditions.

***

#### 📈 **Linear Reward Vesting**

Reward distributions to schUSD holders **vest linearly over a five-day period**, mitigating the risk of “sandwich” attacks — where a user stakes immediately before and unstakes immediately after a reward payment.

This steady vesting curve ensures:

* Fair distribution of rewards across all participants.
* Predictable yield accrual and reduced volatility in vault ratios.

***

#### 🔒 **Minimum Non-Zero Supply**

Each vault enforces a **minimum non-zero schUSD supply** (initially set at 1 chUSD) to protect against _donation attack&#x73;_&#x61;nd rounding exploits.\
This safeguard complements OpenZeppelin’s base protections and ensures the contract’s internal math remains stable at all times.

***

#### 🧭 **Additional Controls**

* **Oracle Verification:** All collateral and NAV data are continuously streamed via **Pyth** for real-time on-chain validation.
* **Institutional Custody:** Assets are held with **BitGo** and other regulated custodians under segregated legal structures.
* **Governance Oversight:** The **GATEKEEPER\_ROLE** actively monitors transactions and can pause minting or staking if anomalous activity is detected.
* **Reserve Fund:** 5 % of collected fees are allocated quarterly to a reserve fund to mitigate black-swan events or unforeseen technical risks.

***

#### ⚖️ **Governance Integrity**

Governance actions are tightly scoped: administrators can adjust cooldown periods, rescue mis-sent non-protocol tokens, and enforce compliance restrictions only under lawful circumstances.\
All operations are logged on-chain and publicly verifiable.

***

**Chateau’s security framework is designed for institutional resilience — combining proven open-source architecture, active monitoring, and prudent governance to protect protocol participants and ensure long-term stability.**
