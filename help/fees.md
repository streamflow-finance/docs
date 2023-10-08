---
description: Streamflow fees explanation
---

# 💰 Fees

**Service fees:** Streamflow charges 0.25% service fee on top of tokens deposited into vesting, payment or token lock contracts on all the supported networks.\
\
**Note:** we also offer custom fees in stable coins, please [book a call](https://calendly.com/streamflow-bd/discovery?month=2023-10) for custom fee offer.

**Network fees:** In addition to the Streamflow fees, standard network gas fees apply to transaction for creating or interacting with contracts.\
\
The gas fee required for creating contracts on Ethereum, BNB Chain, Polygon, Sui and Aptos is same as for making a swap on the given network.

For Solana, the complete breakdown for network fees is given below:

| Name                              | Explanation                                                                                                                                          | Fee                                          | Origin     |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- | ---------- |
| Stream                            | Service fee. **Fully respects the specific vesting/unlocking schedule and is released gradually.\***                                                 | 0.25% on top of the amount that is streaming | Streamflow |
| Associated token account creation | If the recipient doesn't have an account for the token that's being streamed, an associated token account will be created and rent\*\* will be paid. | 0.00407856 SOL                               | Solana     |
| Stream metadata account creation  | Account for storing stream parameters/metadata is created on chain and the rent\* is paid. (1104 bytes)                                              | 0.00857472 SOL                               | Solana     |
| Escrow token account creation     | Escrow\*\*\* token account is created upon stream creation and rent\* is paid.                                                                       | 0.00203928 SOL                               | Solana     |
| Signature                         | Solana charges fees per transaction signature.                                                                                                       | 0.000005 SOL                                 | Solana     |

_(\*) This means that the fee is not fully unlocked upon stream creation, but it is gradually unlocked over the course of the stream._\
_It is important to mention that the fee is charged on top of the amount that is streamed, e.g. if 100 BTC is streamed, the sender account will be debited by 100.25 BTC._\
\_\_\
_(\*\*) Solana network charges storage rent for the account creation._\
_Rent is calculated per storage byte._\
\_\_\
_(\*\*\*) An escrow token account is created upon stream creation. When the recipient withdraws all of the tokens, the escrow account will be closed and rent will be sent to the Streamflow treasury account._

### Streamflow transactions

* **Create stream**\
  \*\*\*\*There are few fees here:\
  \- service fee of 0.25% on top of the amount you are streaming\
  \- metadata account creation fee\
  \- escrow token account creation fee\
  \- 2 \* tx signature fee\
  \
  \- If the recipient doesn't have a token account for the token that is streamed, the associated token account creation fee will be charged.
*   **Top up the stream**\
    \*\*\*\*The service fee is charged.\
    The tx signature fee is charged.

    ***
* **Withdraw**\
  \*\*\*\*On withdraw only tx signature fee is charged.
*   **Transfer**\
    \*\*\*\*On transfer tx signature fee is charged.\
    \
    If the new recipient doesn't have a token account for the token that is transferred the associated token account creation fee will be charged.

    ***
* **Cancel**\
  \*\*\*\*On cancel only tx signature fee is charged.
