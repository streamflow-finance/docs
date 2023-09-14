---
description: Integrate streaming capabilities within a Solana program
---

# Rust SDK

Declare a dependency in your program's Cargo.toml

```
streamflow_sdk = {version = "0.6", features = ["cpi"]}
```

To use protocol on mainnet add sdk with `mainnet` feature

```
streamflow_sdk = {version = "0.6", features = ["cpi", "mainnet"]}
```

Example anchor program invoking streamflow create instruction:

```rust
use anchor_lang::{prelude::*};
use anchor_spl::{
    associated_token::AssociatedToken,
    token::{Mint, Token, TokenAccount},
};

use streamflow_sdk;
use streamflow_sdk::cpi::accounts::Create;

let accs = Create {
    sender: ctx.accounts.sender.to_account_info(),
    sender_tokens: ctx.accounts.sender_tokens.to_account_info(),
    recipient: ctx.accounts.recipient.to_account_info(),
    recipient_tokens: ctx.accounts.recipient_tokens.to_account_info(),
    metadata: ctx.accounts.metadata.to_account_info(),
    escrow_tokens: ctx.accounts.escrow_tokens.to_account_info(),
    streamflow_treasury: ctx.accounts.streamflow_treasury.to_account_info(),
    streamflow_treasury_tokens: ctx.accounts.streamflow_treasury_tokens.to_account_info(),
    withdrawor: ctx.accounts.withdrawor.to_account_info(),
    partner: ctx.accounts.partner.to_account_info(),
    partner_tokens: ctx.accounts.partner_tokens.to_account_info(),
    mint: ctx.accounts.mint.to_account_info(),
    fee_oracle: ctx.accounts.fee_oracle.to_account_info(),
    rent: ctx.accounts.rent.to_account_info(),
    timelock_program: ctx.accounts.streamflow_program.to_account_info(),
    token_program: ctx.accounts.token_program.to_account_info(),
    associated_token_program: ctx.accounts.associated_token_program.to_account_info(),
    system_program: ctx.accounts.system_program.to_account_info(),
};

let cpi_ctx = CpiContext::new(ctx.accounts.streamflow_program.to_account_info(), accs);

streamflow_sdk::cpi::create(
    cpi_ctx,
    start_time,
    net_amount_deposited,
    period,
    amount_per_period,
    cliff,
    cliff_amount,
    cancelable_by_sender,
    cancelable_by_recipient,
    automatic_withdrawal,
    transferable_by_sender,
    transferable_by_recipient,
    can_topup,
    stream_name,
    withdraw_frequency,
    pausable,
    can_update_ra
```

<table><thead><tr><th width="193"></th><th></th></tr></thead><tbody><tr><td><strong>Protocol</strong></td><td>a program that lives on chain, an implementation of Scheduled Token Transfer</td></tr><tr><td><strong>Stream</strong></td><td>an entity that is created by the Protocol, contains information about Token Transfer</td></tr><tr><td><strong>Contract</strong></td><td>a synonym for a Stream. In the code there is no consistency how we name it, in the Protocol we often use <code>Contract</code> referring to a <code>Stream</code>.</td></tr><tr><td><strong>Sender</strong></td><td>an account that creates a Scheduled Token Transfer</td></tr><tr><td><strong>Recipient</strong></td><td>an account that is the receiver of Tokens</td></tr><tr><td><strong>Referral</strong> </td><td>an account that will be used to calculate streamflow and referral fees when creating a Stream</td></tr><tr><td><strong>Partner</strong></td><td>a synonym for a Referral</td></tr><tr><td><strong>Treasury</strong></td><td>a Streamflow account that receives fees as a reward</td></tr><tr><td><strong>Withdrawor</strong></td><td>a Streamflow account that processes automated Token Transfers to the Recipient</td></tr><tr><td><strong>Protocol</strong></td><td>a program that lives on chain, an implementation of Scheduled Token Transfer</td></tr><tr><td><strong>Stream</strong></td><td>an entity that is created by the Protocol, contains information about Token Transfer</td></tr></tbody></table>

