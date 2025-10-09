# Oracles

## Oracle and Data Infrastructure

**Chateau Protocol** relies on a combination of **on-chain oracles** and **off-chain data streams** from institutional RWA partners to ensure accurate valuation, stable collateralization, and real-time system integrity.

These data feeds are central to Chateau’s **mint, redeem, and staking operations**, as well as to **risk management** across both **chUSD** and **schUSD**.

***

### System Architecture

Chateau’s oracle and data architecture is divided into two complementary components:

* **On-chain:** Pyth Network oracles publish validated asset prices and NAV data directly to smart contracts.
* **Off-chain:** Private data streams from RWA partners, and custodians, provide real-time fund performance, loan repayments, and collateral updates.

Together, these sources create a continuously synchronized data layer connecting DeFi transparency with institutional reporting standards.

***

### Price and NAV Feeds

Accurate, low-latency data is critical for Chateau’s **minting, redemption, and portfolio valuation** processes.

* **schUSD valuation** reflects **Covenant VC’s NAV** updates, streamed through verified RWA data partners and reconciled on-chain within the ERC-4626 vault.
* **Collateral management** dynamically adjusts based on feed integrity, liquidity conditions, and exchange or custodian exposure.

> \[!info] Chateau’s pricing system prioritizes accuracy and resilience by combining high-frequency market data with verified off-chain accounting feeds — ensuring consistency across both DeFi and traditional finance domains.

***

### Data Sources

Chateau consumes data from three primary categories:

1. **Pyth Oracles** — on-chain price feeds for digital assets, stablecoins, and key collateral benchmarks.
2. **RWA Partner Streams** — direct encrypted data channels from Covenant VC, fund administrators, and custodians reporting NAV and credit-portfolio metrics.
3. **Market Reference Aggregators** — additional feeds used for validation and redundancy during cross-exchange reconciliation.

***

### Validation and Redundancy

Before each **mint**, **redeem**, or **NAV update**, the protocol validates all incoming data across independent sources.\
\
If a discrepancy is detected between oracle and partner streams, transactions are temporarily halted until verification occurs.

This layered design:

* Prevents price manipulation or oracle drift.
* Protects users during extreme market conditions.
* Ensures all protocol actions are based on auditable, institution-grade data.
