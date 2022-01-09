---
description: Streamflow fees explained
---

# Fees

Streamflow charges service fees.

In addition to the Streamflow fees, Solana network charges certain fees as well.

An overview of fees is presented here:

| Name                          | Explanation                                                                                                         | Fee         | Origin     |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------- | ----------- | ---------- |
| Transaction                   | [https://docs.solana.com/transaction\_fees](https://docs.solana.com/transaction\_fees)                              | 0.0005 SOL  | Solana     |
| Stream account creation       | Account for storing stream parameters is created on chain and the data "rent" is paid.                              | 0.00xxx SOL | Solana     |
| Stream                        | Service fee. Fully respects the specific vesting/unlocking schedule and is released gradually                       | 0.25%       | Streamflow |
| Token account creation        | If the recipient doesn't have an account for the token that's being streamed, an associated token will be created.  |             | Solana     |
| Escrow token account creation | Escrow token account will be created upon stream creation.                                                          |             | Streamflow |

