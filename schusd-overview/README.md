# schUSD Overview

**schUSD** is the yield-bearing counterpart to **chUSD**, forming the second half of **Chateau’s dual-token system**. schUSD earns yield from Covenant VC's Private Credit portfolio. [For more details, read the Fund Partner section.](../fund-partner-covenant-vc/)

Minted when **chUSD** is deposited into **the schUSD 4626 Vault**, schUSD provides holders with exposure to institutional private-credit yields and protocol revenue. The amount of schUSD received upon staking is determined by the prevailing **schUSD-to-chUSD ratio**, which reflects cumulative vault performance and accrued yield.

Over time, as the underlying assets appreciate, the value of schUSD increases relative to chUSD — representing profit accumulation from **Covenant VC’s** fund and Chateau’s market-neutral strategies.

***

### How It Works

When staking:

* Users deposit **chUSD** into the **StakedchUSD** vault and receive **schUSD** in return.
* The **exchange ratio** between schUSD and chUSD automatically adjusts as the vault accrues yield.
* Upon unstaking, schUSD is burned and users receive their proportional share of chUSD, including both principal and accumulated rewards.

There is **no minimum staking period**. Users may stake and unstake in consecutive blocks and still capture proportional returns.



***

### schUSD-to-chUSD Ratio

The **schUSD-to-chUSD ratio** serves as a real-time indicator of cumulative performance.

$$
\text{schUSD Price} = \frac{\text{Total chUSD in Vault}}{\text{Total schUSD Supply}}
$$

This value reflects:

* The total **chUSD** staked in the vault,
* The total **schUSD** outstanding, and
* The **aggregate yield** accumulated since inception.

As underlying assets generate returns, the ratio increases, meaning each schUSD represents a larger claim on the vault’s chUSD holdings.

***

### NAV Updates Methodology

**Net Asset Value (NAV)** for schUSD is updated continuously via **Chateau Protocol’s Pyth oracle** integration.

* **Frequency:** Covenant VC provides NAV data weekly (typically Friday or Saturday).
* **Integration:**
  * NAV ↑ → `transferInRewards` adds new chUSD rewards.
  * NAV ↓ → `retrieve` withdraws chUSD to maintain balance.
* **Reconciliation:** Weekly operations ensure the on-chain schUSD NAV tracks the off-chain fund NAV precisely.

\{{< equation >\}}\
\text{schUSD NAV}_t = \text{schUSD NAV}_{t-1} + \Delta\_{\text{Covenant VC\}} - \text{Fees}\_{t}\
\{{< /equation >\}}

\{% hint style="info" %\}\
Covenant VC adheres to **U.S. GAAP accounting standards**. New loans are recorded at face value, late payments are written off entirely and reinstated only upon collection — resulting in a conservative NAV calculation. Despite this prudence, the fund has maintained a **4.6 % default rate** to date.\
\{% endhint %\}

***

### Transfers & Settlement

To support stable redemptions:

* **Chateau Protocol** coordinates fiat deposits and withdrawals between **Covenant VC’s fund** and its **custodian partner**.
* Transfers are executed in **minimum $10 000 batches** during business days.
* Because bank wires cannot occur atomically, **reported NAV** may temporarily **lag actual NAV** during reconciliation.

***

### Reward Structure

* **Reward Sources:**
  1. Private-credit interest from **Covenant VC**’s lending portfolio.
  2. Funding & basis spreads from Chateau’s hedging operations.
  3. Rewards from stable or staked collateral assets.
* **Vesting:** Rewards **vest linearly over five days**, mitigating front-running risk around yield events.
* **Reserve Fund:** 5 % of collected protocol fees are allocated quarterly to a reserve fund that safeguards against drawdowns or security incidents.

***

### Fees

Chateau applies an **institutional fee structure**:

* **2 % management fee**, deducted monthly from NAV.
* **20 % performance fee**, applied to realized profits.
* **5 % of total fees** allocated quarterly to the **reserve fund**.

$$
\text{Net Yield} = (\text{Gross Yield} - 0.02) \times (1 - 0.20)
$$

***

### Liquidity & Withdrawals

* **Unstaking:** schUSD can be unstaked for chUSD at any time.
* **Cooldown:** Redeemed chUSD is routed to a **Silo contract** and becomes withdrawable after a **30-day cooldown period**.
* **Liquidity Management:** Redemption capacity scales dynamically with portfolio cash flows and custodian balances.\
  See _How Liquid Is It?_ for details.

***

### Technical Architecture

The **StakedchUSD** contract implements the **ERC-4626 Token Vault standard**, enabling full DeFi composability.

Features include:

* Deposits and redemptions with or without slippage thresholds.
* **ERC-2612 Permit** support for gas-efficient staking.
* Open integration for **third-party interfaces and aggregators**, extending schUSD functionality beyond Chateau’s dApp.

***

### Risk Management

Chateau enforces institutional-grade oversight across all vault operations:

* **Oracle Verification:** Real-time collateral and NAV tracking via **Pyth**.
* **Custody:** Assets safeguarded with **BitGo** and regulated trustees under independent legal structures.
* **Governance Controls:** **GATEKEEPER\_ROLE** monitors all staking and minting actions, with authority to freeze operations upon anomalies.
* **No Leverage:** All positions are fully backed and transparently reported.

***

**schUSD transforms institutional private-credit yields into transparent, composable, and programmable on-chain income — bridging Wall Street discipline with DeFi scalability.**
