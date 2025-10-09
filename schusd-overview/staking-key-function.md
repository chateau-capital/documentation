---
description: Important functions of the staking smart contract
---

# Staking Key Function

## Contract Roles and Permissions

The **Chateau Staking and Collateral Contracts** extend the **ERC-4626 Token Vault** standard with added compliance and risk-management functionality, including cooldown periods, sanctioned-address restrictions, and controlled fund-rescue mechanisms.

These controls ensure that **chUSD** and **schUSD** operations remain transparent, secure, and compliant with global regulatory requirements, including **Sanctions**, **Anti-Money Laundering (AML)**, and **Counter-Terrorism Financing (CTF)** regimes.

You can view the deployed **Chateau Staking and Vault contracts** on-chain via [official links.](../security/smart-contracts.md)

***

### Roles in the Chateau Contracts

The staking and vault contracts define **three primary roles**:

* **DEFAULT\_ADMIN\_ROLE**
* **REWARDER\_ROLE**
* **BLACKLISTER\_ROLE**

Each role serves a distinct operational or compliance function within the protocol.

***

### DEFAULT\_ADMIN\_ROLE

The **DEFAULT\_ADMIN\_ROLE** oversees system-level and emergency administrative actions.

This role may:

1. **Set Cooldown Duration**
   * Configures the unstaking cooldown period, up to a maximum of **90 days** from the initial unstake request.
   * The cooldown defines the period between unstake initiation and the time at which users can withdraw **chUSD**.
2. **Rescue Mis-Sent Tokens**
   * Using the `rescueTokens()` function, the admin may recover any ERC-20 tokens **other than chUSD or schUSD** accidentally sent to the contract.
   * This safeguard prevents permanent loss of unrelated tokens while ensuring that core assets remain untouchable.
3. **Redistribute Locked Funds (Compliance Function)**
   * The admin may execute `redistributeLockedAmounts()` to reassign **locked schUSD** originating from sanctioned or blacklisted wallets.
   * This authority exists solely to comply with applicable law and mirrors mechanisms implemented by custodians such as **Circle (USDC)**.
   * Redistribution is limited to **segregated custody wallets** under Chateau’s control and does not apply to general user funds.

***

### REWARDER\_ROLE

The **REWARDER\_ROLE** manages protocol yield inflows.

This role may:

* **Transfer chUSD Rewards into Vaults**
  * Executes `transferInRewards()` to increase the vault’s total balance of **chUSD**, thereby reflecting income from Covenant VC’s portfolio, hedging spreads, or stablecoin rewards.
  * This function powers the growth of **schUSD’s underlying value** over time.

***

### BLACKLISTER\_ROLE

The **BLACKLISTER\_ROLE** enforces regulatory compliance and protects the protocol from exposure to sanctioned or high-risk actors.

This role may:

* Assign or remove the following flags:
  * `SOFT_RESTRICTED_STAKING_ROLE`
  * `FULL_RESTRICTED_STAKING_ROLE`

In practice, only the **Full Restricted** flag is utilized. Addresses holding this flag are:

* Prohibited from **receiving or transferring schUSD**.
* Unable to participate in staking or yield-generating activities.

#### Intended Use

The **BLACKLISTER\_ROLE** is strictly limited to compliance enforcement:

* It is applied **only** when required by law or official court order.
* It targets wallets associated with **sanctioned entities**, **criminal activity**, or **terrorist financing**.
* It is **never used arbitrarily** or at Chateau’s discretion outside these circumstances.

\{% hint style="info" %\}\
These restrictions apply **only to schUSD** staking and yield contracts. Core chUSD minting and redemption functionality remains permissionless for non-restricted addresses.\
\{% endhint %\}

***

### Summary of Role Permissions

| Role                     | Key Functions                                                 | Purpose                           |
| ------------------------ | ------------------------------------------------------------- | --------------------------------- |
| **DEFAULT\_ADMIN\_ROLE** | Set cooldown, recover mis-sent tokens, reassign locked schUSD | Administrative & legal compliance |
| **REWARDER\_ROLE**       | Add chUSD rewards to vault                                    | Revenue distribution              |
| **BLACKLISTER\_ROLE**    | Restrict sanctioned or high-risk addresses                    | AML / Sanctions compliance        |

***

**Chateau’s permission model** ensures operational flexibility while maintaining full compliance with institutional standards and global regulatory frameworks — safeguarding the integrity of both **chUSD** and **schUSD** across jurisdictions.
