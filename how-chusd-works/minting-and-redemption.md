# Minting and Redemption

chUSD may be minted and redeemed by qualified counterparties.

#### Collateral Safeguards

To ensure the integrity of collateral, the majority of chUSD backing is custodied with Chateau Protocol’s regulated custodian partner. Real-time collateral tracking is available via API, providing transparency and oversight into system reserves.\
\
[Collateral Tracking page](https://app.chateau.capital/chusd/collateral)

The transfer of collateral between custodian wallets to minting and redemption smart contract wallets is processed manually, and may take several hours. \
\
Redemptions are processed in a queue on a first come first served basis.

#### **Security and Risk Controls**

**Transaction Limits**\
As a protective measure, chUSD mints and redemptions are capped at $100,000 per block. Continuous transaction monitoring ensures that chUSD remains fully collateralized at all times.

**Emergency Controls**\
Designated _Gatekeeper\_role_ monitors retain the authority to freeze the chUSD contract in the event of malicious activity or a security breach, thereby minimizing potential losses.

**Sanctions Compliance**\
Chateau Protocol enforces strict compliance with U.S. sanctions. Mint and redemption addresses are screened against the Office of Foreign Assets Control (OFAC) lists via ofac-api.com, and blacklisted addresses are prohibited from accessing Chateau Protocol.
