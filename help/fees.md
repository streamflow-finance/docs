---
description: Streamflow fees explanation
---

# Fees

Streamflow charges service fees.

In addition to the Streamflow fees, Solana network charges certain fees as well.

An overview of fees is presented here:

| Name                              | Explanation                                                                                                                                         | Fee            | Origin     |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- | ---------- |
| Stream                            | Service fee. Fully respects the specific vesting/unlocking schedule and is released gradually.                                                      | 0.25%          | Streamflow |
| Associated token account creation | If the recipient doesn't have an account for the token that's being streamed, an associated token account will be created and rent\* will be paid.  | 0.00203928 SOL | Solana     |
| Stream metadata account creation  | Account for storing stream parameters/metadata is created on chain and the rent\* is paid.                                                          | 0.004176 SOL   | Solana     |
| Escrow token account creation     | Escrow\*\* token account is created upon stream creation and rent\* is paid.                                                                        | 0.00407856 SOL | Solana     |
| Signature                         | Solana charges fees per transaction signature.                                                                                                      | 0.000005 SOL   | Solana     |

(\*) In Solana ecosystem when account is created rent for that account's storage must be paid. \
Rent is calculated per storage byte. \
(\*\*) Escrow token account is created upon stream creation to hold tokens until recipient withdraw them. When recipient withdraw all tokens the escrow account will be closed and rent SOL will be returned to the sender.
