---
description: Frequently asked questions
---

# General

#### Which networks does Streamflow support for token distribution? <a href="#what-networks-does-streamflow-support-for-token-distribution" id="what-networks-does-streamflow-support-for-token-distribution"></a>

Streamflow supports:&#x20;

* Solana&#x20;
* Sui
* Ethereum
* BNB Chain
* Polygon
* Aptos

for Token Vesting, Payments and Token Locks.

**Are you getting an error when creating a contract on Streamflow?**

There is a few possible causes. We've provided some general guidance based on support cases we have seen. If you're still blocked after running through these tips, please reach out on Discord in the support channel.&#x20;

1. Ensure you're connected with the **correct wallet**, in case you have multiple wallet extensions / wallet addresses
2. Check that you are on the **correct network**, we support a number of different chains. Especially on the EVM side, double-check that you are connected to the correct network.
3. Check that you have sufficient tokens in your wallet to **pay network fees**. This applies across all networks and additionally with Solana ensure that you have enough SOL to cover the network and rent fees.

**Is Streamflow Protocol permissionless?**

Yes. Streamflow Protocol and app are permissionless to interact with.&#x20;

#### What products and services does Streamflow offer?  <a href="#what-products-and-services-does-streamflow-offer" id="what-products-and-services-does-streamflow-offer"></a>

1. **Vesting contracts:** A contract with a fixed time duration for token distribution to investors, team, community and stakeholder with **linear** or **non-linear** vesting schedule&#x20;
2. **Payment contracts:** A recurring payment contract with an additional option to top-up the contract even after deployment
3. **Token locks:** An immutable contract for locking LP tokens as well as standard tokens&#x20;
4. **Public dashboard:** A publicly shareable dashboard to be transparent with community about token distributions&#x20;
5. **Airdrop distribution:** vested and non-vested airdrop tool

#### How does Streamflow help crypto startups and companies? <a href="#how-does-streamflow-help-crypto-startups-and-companies" id="how-does-streamflow-help-crypto-startups-and-companies"></a>

We help crypto companies to become legally compliant and getting registered in crypto friendly regions.&#x20;

Book a call through Calendly for a consultation: [Streamflow Calendly](https://calendly.com/streamflow-bd/discovery?month=2023-10)​

#### **Does Streamflow charge any fees for its products?** <a href="#does-streamflow-charge-any-fees-for-its-products" id="does-streamflow-charge-any-fees-for-its-products"></a>

Yes. The Streamflow app has a service fee. This **service fee** is 0.19%. In addition to the Streamflow service fee, each Blockchain network that we operate on charges their network fee as well. You can look into the detailed fee structure here: [Fees](https://app.gitbook.com/o/lKQAeTah0SdBXZQDX3ZD/s/2rgfcCgbCvIEZ5qAaV44/\~/diff/\~/revisions/yNUpReQeKmqZ3yYWncGz/help/fees). This service fee applies to vesting contracts, payment contracts and token locks. ​

#### Does Streamflow have SDK for integrations? <a href="#does-streamflow-have-sdk-for-integrations" id="does-streamflow-have-sdk-for-integrations"></a>

Streamflow has two SDK's for integration: JS-SDK and Rust-SDK.&#x20;

**JS-SDK** supports Ethereum L1, BNB Chain, Polygon, Aptos, Sui, and Solana.&#x20;

[https://github.com/streamflow-finance/js-sdk](https://github.com/streamflow-finance/js-sdk)

**Rust-SDK** is currently only supported on Solana.&#x20;

[https://github.com/streamflow-finance/rust-sdk](https://github.com/streamflow-finance/rust-sdk)​

#### Has Streamflow been audited? <a href="#has-streamflow-been-audited" id="has-streamflow-been-audited"></a>

Yes. Security and safety for our users is our paramount concern at all times that's why Streamflow has been audited by four major auditors. These include:&#x20;

1. [**FYEO**](https://www.fyeo.io/) for EVM chains
2. **OPCODES** and [**FYEO**](https://www.fyeo.io/) for Solana&#x20;
3. [**OtterSec**](https://osec.io/) for Aptos&#x20;
4. [**MoveBit** ](https://www.movebit.xyz/)for Sui network.

#### Do you have plans to launch a token? <a href="#do-you-have-plans-to-launch-a-token" id="do-you-have-plans-to-launch-a-token"></a>

Not currently.&#x20;

**Would my assets be affected if the Streamflow UI became unavailable?**

No. All assets on Streamflow are stored on chain and in the highly unlikely event that Streamflow ceases to operate, contracts created with Streamflow remain secure and can only be accessed by the users involved in the contract (recipient, sender). This access would be through the existing SDK.

**How many contracts can I create in one go using CSV?**&#x20;

The amount depends currently on which wallet you are using to create the contracts.&#x20;

Current limits per wallet are:

Backpack: 60

Phantom: 190

Solflare: 300
