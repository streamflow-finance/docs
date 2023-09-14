---
description: Build an app on top of the Streamflow protocol
---

# Overview

Streamflow is fully composable, supporting integration with various protocols via the Streamflow SDK. At the core of **Streamflow** is a protocol for streaming payments, that acts like a time-lock escrow service for funds.&#x20;

Streamflow Protocol allows the creation of scheduled Token Transfers from one account to another. This transfer may be done in the form of an actual token transfer on the chain to a Recipient address or just as an unlock, meaning that after a certain time, the Recipient may claim Tokens manually.&#x20;

The schedule may be configured to send/unlock these tokens partially with some amount (absolute value) being unlocked every unlock period. The Sender may also configure a cliff - a one-time unlock of a certain amount (different from the usual unlock amount configured in the Stream) -that will be done as the first unlock.

## Streamflow SDK

&#x20;[_**app.streamflow.finance**_](https://app.streamflow.finance/?utm\_medium=github.com\&utm\_source=referral\&utm\_campaign=js-sdk-repo) _is a React application that uses Streamflow's JS SDK directly._

* Use the [**JS SDK**](https://github.com/streamflow-finance/js-sdk) to interact with the protocol => [NPM package](https://www.npmjs.com/package/@streamflow/stream)
* Use the [**Rust SDK**](https://github.com/streamflow-finance/rust-sdk) to integrate within a Solana program => [Rust Crate](https://docs.rs/streamflow-sdk/)

## Methods

A protocol is a Program that lives on-chain. To interact with the Streamflow protocol you'll need to make use of pre-defined Methods, which are called within the blockchain transaction.

<details>

<summary>create</summary>

**Authority:** Anyone

Creates a Stream, usually accepts these parameters

```rust
	amount: u64,
        period: u64,
        amount_per_period: u64,
        start: u64,
        cliff_amount: u64,
        cancelable_by_sender: bool,
        cancelable_by_recipient: bool,
        transferable_by_sender: bool,
        transferable_by_recipient: bool,
        can_topup: bool,
        pausable: bool,
        can_update_rate: bool,
        automatic_withdrawal: bool,
        withdrawal_frequency: u64,
        contract_name: vector<u8>,
        recipient: address,
        partner: address,
```

All other parameters that are part of stream structure are calculated.



Validations:

```rust
assert!(amount_per_period <= amount, EBAD_INPUT_AMOUNT_PER_PERIOD);
assert!(amount_per_period > 0, EBAD_INPUT_AMOUNT_PER_PERIOD);

if (cliff_amount > 0) {
    assert!(cliff_amount <= amount, EBAD_INPUT_CLIFF_AMOUNT);
};
assert!(period > 0, EBAD_INPUT_PERIOD);
assert!(withdrawal_frequency == 0 || withdrawal_frequency >= period, EBADINPUT);

assert!(now <= start, EBAD_INPUT_START);
assert!(start < now + SEVENTY_YEARS_IN_SECS, EBAD_INPUT_START);
```

</details>

<details>

<summary>update</summary>

**Authority:** Sender

Updates a Stream, usually accepts these parameters

```rust
				automatic_withdrawal: Option<bool>,
        withdrawal_frequency: Option<u64>,
        amount_per_period: Option<u64>,
```

All parameters are optional.

* `withdrawal_frequency` is used only if `automatic_withdrawal` parameter is set to `true`
* `update` allows only to **enable** `automatic_withdrawal` (disabling may be tricky because we also need to notify Worker for that, **but in theory we can allow disabling AW**)
* `amount_per_period` is accepted only if `can_update_rate` is enabled



</details>

<details>

<summary>Cancel</summary>

**Authority:** configured by `cancelable_by_sender` and `cancelable_by_recipient` flags

Cancel a Stream.

* all unlocked funds by the time of cancellation are withdrawn (including fees)
* all leftover funds are returned to the Sender (including fees)

</details>

<details>

<summary>Pause</summary>

**Authority:** Sender if `pausable` is enabled

Pause a Stream

* when stream is paused, unlock calculation is halted
* all already unlocked funds may be withdrawn

</details>

<details>

<summary>Unpause</summary>

**Authority:** Sender if `pausable` is enabled and stream is in `pause` state

Unpauses a Stream

* continue unlock calculation

</details>

<details>

<summary>Withdraw</summary>

**Authority:** Recipient or Withdrawor if `automatic_withdrawal` is enabled

Withdraw some amount to Recipient address, usually accepts these parameters

```rust
amount: u64
```

* accepts `18446744073709551615` as magical number to withdraw **all unlocked funds**
* can’t withdraw more than unlocked
* fees are transferred according to withdrawn amount

</details>

<details>

<summary>Transfer</summary>

**Authority:** configured by `transferable_by_sender` and `transferable_by_recipient` flags

Change Recipient address, usually accepts these parameters

```rust
				new_recipient: address
```

* on transfer unlocked funds **remain in a stream** (so new recipient can withdraw them)

</details>
