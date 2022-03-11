---
description: Frequently asked questions
---

# FAQ

### What’s the difference between community and commercial versions of Streamflow token vesting?

**The Community version** of token vesting is free to use and has no service fees. It has a limited feature set compared to the commercial version. Contracts are not transferable.

Streamflow (**commercial**) token vesting app also comes up with powerful additional features such as giving a Subject/Title to the contract, auto-withdrawal feature, referral system. You can also choose who gets the authority to cancel or transfer the vesting contract stream from the sender/recipient. This version has [fees.md](fees.md "mention").

**Streamflow app:** [**https://app.streamflow.finance**](https://app.streamflow.finance/vesting)****

Community version (SPL token vesting): [https://free.streamflow.finance/vesting](https://free.streamflow.finance/vesting)

### How is a token vesting stream different from a payroll stream?

1\. You can set up a cliff time and release percentage (at specified cliff time) for a vesting contract stream while there is no such option in a payroll stream.

2\. You can top-up a payroll stream while there is no such option in a vesting contract stream.

### Are funds returned to the sender if a vesting contract or a payroll stream is canceled?

In case a live vesting contract or a payroll stream is canceled, locked tokens are returned to the sender and unlocked tokens are automatically withdrawn into the recipient wallet.

### **What happens to the funds if a vesting contract or a payroll stream is transferred to a new address?**

In case a live vesting contract stream or a payroll stream is transferred to a new address, the stream gets transferred to the new recipient including the unlocked amount (that has not been withdrawn by the previous recipient).

### **Which tokens are supported by Streamflow for vesting and payroll streams? How to stream SOL?**

Streamflow supports all SPL tokens for vesting and payroll streams. In other words, all Solana network tokens are supported. In order to stream SOL, it should be converted into the wrapped SOL token. Network native SOL is a coin that can only be used for gas fees and can not be directly used in smart contracts such as vesting or payroll streams without wrapping it into a token. The Streamflow interface will only read wrapped SOL balance for streams.&#x20;

### **Does Streamflow charge any fees for its products?**

The Streamflow V2 has a small service fee of 0.25% on top of the amount being streamed. In addition to the Streamflow service fee, Solana network charges certain fees as well. It is recommended to have at least 0.02 SOL in the wallet to avoid failed transactions. You can look into the detailed fee structure here: [fees.md](fees.md "mention")

Streamflow does not charge any service fee on the free (community) version of vesting.

### Do you have plans to launch a token? What will be its utility?

Yes, Streamflow has plans of launching its native token ‘STRM’. Tokenomics and launch schedule are yet to be announced.&#x20;

### **What other products does Streamflow plan to launch in the future?**

Currently, Streamflow has two products live on mainnet, token vesting and payroll streams. We have plans to launch more products such as multi-signature vaults and batch payments in near future. Streamflow will continuously innovate and expand its products and services over time.

### **Who is the team behind this?**

{% content-ref url="../streamflow/team.md" %}
[team.md](../streamflow/team.md)
{% endcontent-ref %}



_If your question is missing, head over to_ [_our Discord_ ](https://discord.gg/jHa4Q9vAwD)_and ask in the #feedback channel. :)_
