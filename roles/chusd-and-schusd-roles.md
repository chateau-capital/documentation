# chUSD and schUSD roles

DEFAULT\_ADMIN\_ROLE

*   Can grant and revoke all other roles

    * Can add/remove supported assets
    * Can add/remove custodian addresses
    * Can set maximum mint per block limit
    * Can set maximum redeem per block limit
    * Can transfer ownership to new admin



GATEKEEPER\_ROLE

* Can disable minting functionality in emergencies
  * Can disable redemption functionality in emergencies
  * Can remove minters in emergency situations
  * Can remove redeemers in emergency situations
  * Acts as an emergency control mechanism
  * Cannot add new roles or modify system parameters

\
MINTER\_ROLE

* Can mint new USDe tokens
  * Can execute mint() function
  * Can execute mintWETH() function
  * Must follow block limits for minting
  * Cannot modify system parameters
  * Cannot add/remove other roles\


REDEEMER\_ROLE

*   Can redeem USDe tokens for collateral

    * Can execute redeem() function
    * Must follow block limits for redemption
    * Cannot modify system parameters
    * Cannot add/remove other roles



COLLATERAL\_MANAGER\_ROLE

* Can transfer collateral to cust<sub>o</sub>dy wallets
  * Manages collateral distribution
  * Cannot mint or redeem tokens
  * Cannot modify system parameters
  * Cannot add/remove other roles



\
\
