---
description: Streamflow fees explanation
---

# Fees

Streamflow charges service fees.&#x20;

In addition to the Streamflow fees, Solana network charges certain fees as well.

An overview of fees is presented here:

| Name                              | Explanation                                                                                                                                           | Fee                                          | Origin     |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------- | ---------- |
| Stream                            | Service fee. **Fully respects the specific vesting/unlocking schedule and is released gradually.\***                                                  | 0.25% on top of the amount that is streaming | Streamflow |
| Associated token account creation | If the recipient doesn't have an account for the token that's being streamed, an associated token account will be created and rent\*\* will be paid.  | 0.00407856 SOL                               | Solana     |
| Stream metadata account creation  | Account for storing stream parameters/metadata is created on chain and the rent\* is paid.                                                            | 0.004176 SOL                                 | Solana     |
| Escrow token account creation     | Escrow\*\*\* token account is created upon stream creation and rent\* is paid.                                                                        | 0.00203928 SOL                               | Solana     |
| Signature                         | Solana charges fees per transaction signature.                                                                                                        | 0.000005 SOL                                 | Solana     |

_(\*) This means that the fee is not fully unlocked upon stream creation, but it is gradually unlocked over the course of the stream._ \
_It is important to mention that the fee is charged on top of the amount that is streamed,              e.g. if 100 BTC is streamed, the sender account will be debited by 100.25 BTC._\
__\
_(\*\*)  Solana network charges storage rent for the account creation._\
_Rent is calculated per storage byte._ \
__\
_(\*\*\*) An escrow token account is created upon stream creation. When the recipient withdraws all of the tokens, the escrow account will be closed and rent will be sent to streamflow treasury account._

### StreamFlow transactions

* **Create stream**\
  ****There are few fees here:\
  &#x20; \- service fee of 0.25% on top of the the amount you are streaming,\
  &#x20; \- metadata account creation fee,\
  &#x20; \- escrow token account creation fee,\
  &#x20; \- 2 \* tx signature fee.\
  \
  &#x20; \- If the recipient doesn't have token account for the token that is streamed the associated token account creation fee will be charged.\

* **Top up stream**\
  ****The service fee is charged.\
  The tx signature fee is charged.\
  ****
* **Withdraw**\
  ****On withdraw only tx signature fee is charged.\

* **Transfer**\
  ****On transfer tx signature fee is charged.\
  \
  If new recipient doesn't have token account for the token that is transferred the associated token account creation fee will be charged.\
  ****
* **Cancel**\
  ****On cancel only tx signature fee is charged.

__
