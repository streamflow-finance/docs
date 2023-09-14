---
description: Interact with the protocol to create streams and vesting contracts
---

# Javascript SDK

This package allows you to `create`, `createMultiple`, `withdraw`, `cancel`, `topup`, `transfer`, `update` a token stream. You can also `getOne` stream and `get` multiple streams.

## Installation

`npm i -s @streamflow/stream`

or

`yarn add @streamflow/stream`

***

## Import SDK

Most common imports:

```
import { BN } from "bn.js";
import { Types, GenericStreamClient, getBN, getNumberFromBN } from "@streamflow/stream";
```

_Check the SDK for other types and utility functions._

***

## Create StreamClient instance

Before creating and manipulating streams, a chain-specific or generic `StreamClient` instance must be created. All stream functions are methods in this instance.

#### Solana

```javascript
import {
  StreamflowSolana,
  Types,
} from "@streamflow/stream";

const solanaClient = new StreamflowSolana.SolanaStreamClient(
  "https://api.mainnet-beta.solana.com"
);
```

#### Aptos

```javascript
import {
  StreamflowAptos,
  Types,
} from "@streamflow/stream";

const aptosClient = new StreamflowAptos.AptosStreamClient(
  "https://fullnode.mainnet.aptoslabs.com/v1"
);
```

#### Ethereum

```javascript
import {
  StreamflowEVM,
  Types,
} from "@streamflow/stream";

const ethereumClient = new StreamflowEVM.EvmStreamClient(
  "YOUR_ETHEREUM_NODE_URL",
  Types.IChain.Ethereum,
  signer // will be sender in a stream and authority for all stream related transactions
);
```

#### Polygon

```javascript
import {
  StreamflowEVM,
  Types,
} from "@streamflow/stream";

const polygonClient = new StreamflowEVM.EvmStreamClient(
  "YOUR_POLYGON_NODE_URL",
  Types.IChain.Polygon,
  signer // will be sender in a stream and authority for all stream related transactions
);
```

#### BNB Smart Chain

```javascript
import {
  StreamflowEVM,
  Types,
} from "@streamflow/stream";

const bnbClient = new StreamflowEVM.EvmStreamClient(
  "https://bsc-dataseed1.binance.org/",
  Types.IChain.BNB,
  signer // will be sender in a stream and authority for all stream related transactions
);
```

***

## Generic Stream Client

`GenericStreamClient` provides an isomorphic interface to work with streams agnostic of the chain.

```javascript
import { GenericStreamClient, Types } from "@streamflow/stream";

const client =
  new GenericStreamClient<Types.IChain.Solana>({
    chain: Types.IChain.Solana, // Blockchain
    clusterUrl: "https://api.mainnet-beta.solana.com", // RPC cluster URL
    cluster: Types.ICluster.Mainnet, // (optional) (default: Mainnet)
    // ...rest chain specific params e.g. commitment for Solana
  });
```

***

## **Create stream**

Creating a stream requires a wallet with tokens for gas fees.&#x20;

```javascript
const createStreamParams: Types.ICreateStreamData = {
  recipient: "4ih00075bKjVg000000tLdk4w42NyG3Mv0000dc0M00", // Recipient address.
  tokenId: "DNw99999M7e24g99999999WJirKeZ5fQc6KY999999gK", // Token mint address.
  start: 1643363040, // Timestamp (in seconds) when the stream/token vesting starts.
  amount: getBN(100, 9), // depositing 100 tokens with 9 decimals mint.
  period: 1, // Time step (period) in seconds per which the unlocking occurs.
  cliff: 1643363160, // Vesting contract "cliff" timestamp in seconds.
  cliffAmount: new BN(10), // Amount unlocked at the "cliff" timestamp.
  amountPerPeriod: getBN(5, 9), // Release rate: how many tokens are unlocked per each period.
  name: "Transfer to Jane Doe.", // The stream name or subject.
  canTopup: false, // setting to FALSE will effectively create a vesting contract.
  cancelableBySender: true, // Whether or not sender can cancel the stream.
  cancelableByRecipient: false, // Whether or not recipient can cancel the stream.
  transferableBySender: true, // Whether or not sender can transfer the stream.
  transferableByRecipient: false, // Whether or not recipient can transfer the stream.
  automaticWithdrawal: true, // Whether or not a 3rd party (e.g. cron job, "cranker") can initiate a token withdraw/transfer.
  withdrawalFrequency: 10, // Relevant when automatic withdrawal is enabled. If greater than 0 our withdrawor will take care of withdrawals. If equal to 0 our withdrawor will skip, but everyone else can initiate withdrawals.
  partner: null, //  (optional) Partner's wallet address (string | null).
};

const solanaParams = {
    sender: wallet, // SignerWalletAdapter or Keypair of Sender account
    isNative: // [optional] [WILL CREATE A wSOL STREAM] Wether Stream or Vesting should be paid with Solana native token or not
};

const aptosParams = {
    senderWallet: wallet, // AptosWalletAdapter Wallet of sender
};

const ethereumParams = undefined;

try {
  const { ixs, tx, metadata } = await client.create(createStreamParams, solanaParams); // second argument differ depending on a chain
} catch (exception) {
  // handle exception
}
```

<table><thead><tr><th width="193"></th><th></th></tr></thead><tbody><tr><td><strong>Protocol</strong></td><td>a program that lives on chain, an implementation of Scheduled Token Transfer</td></tr><tr><td><strong>Stream</strong></td><td>an entity that is created by the Protocol, contains information about Token Transfer</td></tr><tr><td><strong>Contract</strong></td><td>a synonym for a Stream. In the code there is no consistency how we name it, in the Protocol we often use <code>Contract</code> referring to a <code>Stream</code>.</td></tr><tr><td><strong>Sender</strong></td><td>an account that creates a Scheduled Token Transfer</td></tr><tr><td><strong>Recipient</strong></td><td>an account that is the receiver of Tokens</td></tr><tr><td><strong>Referral</strong> </td><td>an account that will be used to calculate streamflow and referral fees when creating a Stream</td></tr><tr><td><strong>Partner</strong></td><td>a synonym for a Referral</td></tr><tr><td><strong>Treasury</strong></td><td>a Streamflow account that receives fees as a reward</td></tr><tr><td><strong>Withdrawor</strong></td><td>a Streamflow account that processes automated Token Transfers to the Recipient</td></tr><tr><td><strong>Protocol</strong></td><td>a program that lives on chain, an implementation of Scheduled Token Transfer</td></tr><tr><td><strong>Stream</strong></td><td>an entity that is created by the Protocol, contains information about Token Transfer</td></tr></tbody></table>

***

## Create multiple streams at once

```javascript
const recipients = [
  {
    recipient: "4ih00075bKjVg000000tLdk4w42NyG3Mv0000dc0M00", // Solana recipient address.
    amount: getBN(100, 9), // depositing 100 tokens with 9 decimals mint.
    name: "January Payroll", // The stream name/subject.
    cliffAmount: getBN(10, 9), // amount released on cliff for this recipient
    amountPerPeriod: getBN(1, 9), //amount released every specified period epoch
  },
];
const createStreamParams: Types.ICreateMultipleStreamData = {
  recipients: recipients, // Solana recipient address.
  tokenId: "DNw99999M7e24g99999999WJirKeZ5fQc6KY999999gK", // SPL Token mint.
  start: 1643363040, // Timestamp (in seconds) when the stream/token vesting starts.
  period: 1, // Time step (period) in seconds per which the unlocking occurs.
  cliff: 1643363160, // Vesting contract "cliff" timestamp in seconds.
  canTopup: false, // setting to FALSE will effectively create a vesting contract.
  cancelableBySender: true, // Whether or not sender can cancel the stream.
  cancelableByRecipient: false, // Whether or not recipient can cancel the stream.
  transferableBySender: true, // Whether or not sender can transfer the stream.
  transferableByRecipient: false, // Whether or not recipient can transfer the stream.
  automaticWithdrawal: true, // Whether or not a 3rd party (e.g. cron job, "cranker") can initiate a token withdraw/transfer.
  withdrawalFrequency: 10, // Relevant when automatic withdrawal is enabled. If greater than 0 our withdrawor will take care of withdrawals. If equal to 0 our withdrawor will skip, but everyone else can initiate withdrawals.
  partner: null, //  (optional) Partner's wallet address (string | null).
};

const solanaParams = {
    sender: wallet, // SignerWalletAdapter or Keypair of Sender account
    isNative: // [optional] [WILL CREATE A wSOL STREAM] Wether Stream or Vesting should be paid with Solana native token or not
};

const aptosParams = {
    senderWallet: wallet, // AptosWalletAdapter Wallet of sender
};

const ethereumParams = undefined;

try {
  const { txs } = await client.createMultiple(createMultiStreamsParams, solanaParams);
} catch (exception) {
  // handle exception
}
```

***

## Identifying created contracts (streams or vesting)

All Stream Clients return `Types.ICreateResult` object (`createdMultiple` returns an Array) that has the following structure

```
interface ICreateResult {
  ixs: (TransactionInstruction | Types.TransactionPayload)[];
  txId: string;
  metadataId: MetadataId;
}
```

`metadataId` is the id of the created stream.

***

## Interacting with existing streams

{% tabs %}
{% tab title="Withdraw from stream" %}
```javascript
const withdrawStreamParams: Types.IWithdrawData = {
  id: "AAAAyotqTZZMAAAAmsD1JAgksT8NVAAAASfrGB5RAAAA", // Identifier of a stream to be withdrawn from.
  amount: getBN(100, 9), // Requested amount to withdraw. If stream is completed, the whole amount will be withdrawn.
};

const solanaParams = {
    invoker: wallet, // SignerWalletAdapter or Keypair signing the transaction
};

const aptosParams = {
    senderWallet: wallet, // AptosWalletAdapter Wallet of wallet signing the transaction
    tokenId: "0x1::aptos_coin::AptosCoin", // Aptos Coin type
};

const ethereumParams = undefined;

try {
  const { ixs, tx } = await client.withdraw(withdrawStreamParams, solanaParams);
} catch (exception) {
  // handle exception
}
```
{% endtab %}

{% tab title="Topup stream" %}
Topping up a stream allows you to add funds to an existing contract and extend the duration of the stream/vesting.&#x20;

```javascript
const topupStreamParams: Types.ITopUpData = {
  id: "AAAAyotqTZZMAAAAmsD1JAgksT8NVAAAASfrGB5RAAAA", // Identifier of a stream to be topped up.
  amount: getBN(100, 9), // Specified amount to topup (increases deposited amount).
};

const solanaParams = {
    invoker: wallet, // SignerWalletAdapter or Keypair signing the transaction
    isNative: // [ONLY FOR wSOL STREAMS] [optional] Wether topup is with Native Solanas
};

const aptosParams = {
    senderWallet: wallet, // AptosWalletAdapter Wallet of wallet signing the transaction
    tokenId: "0x1::aptos_coin::AptosCoin", // Aptos Coin type
};

const ethereumParams = undefined;

try {
  const { ixs, tx } = await client.topup(topupStreamParams, solanaParams);
} catch (exception) {
  // handle exception
}
```
{% endtab %}

{% tab title="Transfer stream " %}
Transfer stream to another recipient

```javascript
const data: Types.ITransferData = {
  id: "AAAAyotqTZZMAAAAmsD1JAgksT8NVAAAASfrGB5RAAAA",
  newRecipient: "99h00075bKjVg000000tLdk4w42NyG3Mv0000dc0M99", // Identifier of a stream to be transferred.
};

const solanaParams = {
    invoker: wallet, // SignerWalletAdapter or Keypair signing the transaction
};

const aptosParams = {
    senderWallet: wallet, // AptosWalletAdapter Wallet of wallet signing the transaction
    tokenId: "0x1::aptos_coin::AptosCoin", // Aptos Coin type
};

const ethereumParams = undefined;

try {
  const { tx } = await client.transfer(data, solanaParams);
} catch (exception) {
  // handle exception
}
```


{% endtab %}

{% tab title="Cancel stream" %}
```javascript
const cancelStreamParams: Types.ICancelData = {
  id: "AAAAyotqTZZMAAAAmsD1JAgksT8NVAAAASfrGB5RAAAA", // Identifier of a stream to be canceled.
};

const solanaParams = {
    invoker: wallet, // SignerWalletAdapter or Keypair signing the transaction
};

const aptosParams = {
    senderWallet: wallet, // AptosWalletAdapter Wallet of wallet signing the transaction
    tokenId: "0x1::aptos_coin::AptosCoin", // Aptos Coin type
};

const ethereumParams = undefined;

try {
  const { ixs, tx } = await StreamClient.cancel(cancelStreamParams, solanaParams);
} catch (exception) {
  // handle exception
}
```


{% endtab %}
{% endtabs %}

***

## Get one stream by its ID

```javascript
const data: Types.IGetOneData = {
  id: "AAAAyotqTZZMAAAAmsD1JAgksT8NVAAAASfrGB5RAAAA", // Identifier of a stream
};

try {
  const stream = await client.getOne(data);
} catch (exception) {
  // handle exception
}
```

***

## Get multiple streams for a specific wallet address

```javascript
const data: Types.IGetAllData = {
  address: "99h00075bKjVg000000tLdk4w42NyG3Mv0000dc0M99",
  type: Types.StreamType.All,
  direction: Types.StreamDirection.All,
};

try {
  const streams = client.get(data);
} catch (exception) {
  // handle exception
}
```

***

## Fetching unlocked amount

```javascript
const stream = await client.getOne({
  id: "AAAAyotqTZZMAAAAmsD1JAgksT8NVAAAASfrGB5RAAAA",
});

const unlocked = stream.unlocked(tsInSeconds); // bn amount unlocked at the tsInSeconds
console.log(getNumberFromBN(unlocked, 9));
```

* Note: unlocked amount is determined based on configuration set on creation, no dynamic data is involved.

***

## Reading withdrawn amount and remaining funds

```javascript
const stream = await client.getOne({
  id: "AAAAyotqTZZMAAAAmsD1JAgksT8NVAAAASfrGB5RAAAA",
});
const withdrawn = stream.withdrawnAmount; // bn amount withdrawn already
console.log(getNumberFromBN(wihtdrawn, 9));
const remaining = stream.remaining(9); // amount of remaining funds
console.log(remaining);
```

***

Please note that transaction fees for the scheduled transfers are paid upfront by the stream creator (sender).

Our Github: [https://github.com/streamflow-finance](https://github.com/streamflow-finance)

To see some examples of what you can build with Streamflow, check out:\
&#x20;[https://streamflow.finance/integrations](https://streamflow.finance/integrations).
