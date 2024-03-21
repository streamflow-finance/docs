---
description: Breakdown of our fee structure
---

# Costs of using Streamflow

**Service fees:** Streamflow charges a default service fee of 0.19%. This fee is presently taken as the contract unlocks which aligns our incentives alongside the creator of the contract.\
\
Note: Reach out to us for a custom fee offer, we recommend booking a call with us [Book a call](https://calendly.com/streamflow-bd/token-vesting)

**Network fees:** In addition to the Streamflow fees, standard network gas fees apply to transactions for creating or interacting with contracts.\
\
The gas fee required for creating contracts on **Ethereum**, **BNB Chain**, **Polygon**, **Sui** and **Aptos** is same as for making a swap on the given network.\
\
The blockchain fees per contract on **Solana** are approximately **0.01469256 SOL,** complete breakdown for Solana network fess per contract is given at the bottom

#### Streamflow transactions <a href="#streamflow-transactions" id="streamflow-transactions"></a>

* **Create Contract**
  * Streamflow service fee (see above)
  * Network fees
  * Rent (Solana specific)
* **Top up Contract**
  * The same fees are charged as above for the newly topped up amount
* **Manual Withdraw**
  * The network fee is paid by the recipient on the withdraw transaction
* **Auto-claim fees**
  * In case sender enables auto-claim feature for the contract, the transaction fee is paid by the sender for each auto-claim that happens
* **Transfer**
  * The network fee is charged on transaction for transferring the contract
    * Note: If the new recipient doesn't have a token account for the token that is transferred, the associated token account creation fee will be charged.
* **Cancel**
  * The network fee is charged on transaction for canceling the contract

For Solana, the complete breakdown for network fees is given below:

| Name                               | Explanation                                                                                                                                                        | Fee                                                     | Origin     |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------- | ---------- |
| Contract                           | Service fee. **Fully respects the specific vesting/unlocking schedule and is released gradually.**                                                                 | 0.19% on top of the amount that is scheduled for unlock | Streamflow |
| Associated token account creation  | If the recipient doesn't have an account for the token that's being progressively unlocked, an associated token account will be created and rent\*\* will be paid. | 0.00407856 SOL                                          | Solana     |
| Contract metadata account creation | Account for storing contract parameters/metadata is created on chain and the rent\* is paid. (1104 bytes)                                                          | 0.00857472 SOL                                          | Solana     |
| Escrow token account creation      | Escrow\*\*\* token account is created upon contract creation and rent\* is paid.                                                                                   | 0.00203928 SOL                                          | Solana     |
| Signature                          | Solana charges fees per transaction signature.                                                                                                                     | 0.000005 SOL                                            | Solana     |

_\* This means that the fee is not fully unlocked upon contract creation, but it is gradually unlocked over the course of the contract. It is important to mention that the fee is charged on top of the amount that is unlocking, e.g. if 100 BTC is unlocked, the sender account will be debited by 100.25 BTC._

_\*\* Solana network charges storage rent for the account creation._ _Rent is calculated per storage byte._

_\*\*\* An escrow token account is created upon stream creation. When the recipient withdraws all of the tokens, the escrow account will be closed and rent will be sent to the Streamflow treasury account._

#### &#x20;<a href="#streamflow-transactions" id="streamflow-transactions"></a>
