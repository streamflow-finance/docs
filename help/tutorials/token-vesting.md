---
description: A short tutorial on how to set up vesting contracts using Streamflow app
---

# 💰 Token Vesting

Streamflow token vesting app is the most efficient way to vest SPL tokens to investors, teams, and communities.

Let’s go through a step-by-step process of creating a vesting contract using Streamflow.

#### Step 1: Connect the wallet

Firstly, you need to visit the Streamflow app via the following URL:

👉 [app.streamflow.finance](https://bit.ly/3igHaDj)

Next, you will have to connect the wallet to start using the app. Streamflow supports multiple wallet providers, such as Phantom, Solfare, Slope, and Sollet.

#### Step 2: **Vesting amount, recipient address, and (optional) email address**

Enter the total number of tokens to be vested in the amount tab, and paste the recipient's SPL wallet address in the given tab. You can also add the recipient's email address, an email is sent to the recipient regarding the creation of vesting contract. Additionally, the recipient gets notified when unlocked tokens are transferred into the wallet.                  &#x20;

![Vesting amount, recipient address and recipient email](<../../.gitbook/assets/github vesting 1.JPG>)

#### Step 3: **Contract title, vesting duration, and release frequency**

The subject of the vesting contract can be typed in the contract title tab, you will also have to select the start and end date/time of the vesting contract duration. Release frequency can be chosen in the form of multiple time units, such as second, minute, hour, day, week, month, and year. A proportional amount of the vested tokens will be released in accordance with release frequency.              &#x20;

![Subject/title, vesting duration and release frequency](<../../.gitbook/assets/devnet 3 shot.png>)

#### Step 4: **Cliff time release and cancel/transfer permission**

By using the cliff time release feature, a certain percentage of the total vested tokens can be released at the first flow/unlock of the vested funds. For example, if you set the cliff time release at 10%, ten percent of the total vested tokens will be released as soon as the vesting contract starts streaming tokens, and the recipient will immediately be able to withdraw those unlocked tokens. ****&#x20;

You can also choose who gets the authority to cancel or transfer the vesting contract stream from the sender/recipient.                &#x20;

![Cliff time release & cancel/transfer permissions](<../../.gitbook/assets/Screenshot (21).png>)

#### Step 5: Automatic withdrawal, referral address and overview

Automatic withdrawal is a quite handy feature, it will automatically transfer the unlocked tokens into the recipient’s wallet at the set frequency.

&#x20;In case someone referred you to Streamflow, just paste the wallet address of the referrer in the referral address tab, and a portion of the service fees will be sent to that address as a reward.              &#x20;

![                                                  Automatic withdrawal                                                        ](<../../.gitbook/assets/devnet shot 5.png>)

![Referral address](<../../.gitbook/assets/ref address].JPG>)

Finally, take a look at the overview tab to see all the parameters of your vesting contract, click on the 'create vesting contract' button, and approve the transaction in your wallet. Your vesting contract will go live on the Solana network as soon as the transaction is confirmed.               &#x20;

![Overview tab](<../../.gitbook/assets/overview vesting.JPG>)

![Click this and approve the transaction](../../.gitbook/assets/image\_2022-04-27\_135420070.png)

The sender will be able to see and interact with the vesting contract on the 'outgoing streams' page. On the other hand, the recipient will be able to see and interact with the vesting contract on the 'incoming streams' page.&#x20;

### Video tutorial&#x20;

{% embed url="https://youtu.be/QFjTMXL6uDc" %}
How to use Token Vesting on StreamFlow Finance
{% endembed %}
