---
description: A complete guide on creating vesting contracts on the Streamflow app
---

# Create a Vesting Contract

{% embed url="https://www.loom.com/share/614e86c2919b440f8b5f77e987643abb?sid=c8e4c13a-5111-436f-913e-ee0dfa78c751" %}
Streamflow token vesting
{% endembed %}

\
Let’s go through a step-by-step process of creating token vesting contracts using Streamflow.

#### Step 1: Connect the wallet

Firstly, you need to visit the Streamflow app via the following URL:

👉 [app.streamflow.finance](https://bit.ly/3igHaDj)

Next, you will have to connect the wallet to start using the app. We support a variety of wallets on Ethereum L1, BNB Chain, Polygon, Solana, Aptos and Sui network.

\
**Step 2:** **Configure token, vesting duration and unlock schedule**

<figure><img src="../.gitbook/assets/image (11).png" alt="" width="375"><figcaption></figcaption></figure>

Select the **"Token"** of your choice that you want to vest from the drop-down list of the tokens available in your wallet. You will also be able to see the token balance.

Next, you need to select the **"Vesting Duration"**, this is the total time of your contract.

**"Unlock Schedule"** comes next and that can be understood as how often the tokens will unlock to the recipient. A brief example, if you configure a Vesting Duration of 1 year with a monthly Unlock Schedule - the recipient will receive tokens once per month.&#x20;

**Step 3:** **Cliff time release and cancel/transfer permissionn**

<figure><img src="../.gitbook/assets/image (12).png" alt="" width="375"><figcaption></figcaption></figure>

Next up, you'll configure when the contract will begin to vest the tokens. You have the option of scheduling the contract to start at a future date and time or alternatively starting the contract immediately upon creation.&#x20;

When you **"Add Cliff Amount"**, a certain percentage of the total vested tokens can be released with the first unlock of the vested funds.

As an example if you set the cliff time release at 10%, ten percent of the total vested tokens will be released to the recipient as soon as the vesting contract starts&#x20;

With **"Auto-Claim"** you can automate the need for the recipient to claim their tokens as they unlock. Instead the unlocked tokens are directly dropped into the recipients wallet. The sender will pay the fees for these transactions. &#x20;

Lastly, you can select who can **cancel** the contract as well as who can **transfer** and change the recipient address.&#x20;

\
**Step 4: Adding recipient(s) with vesting amount, address, contract title, and email address**

<figure><img src="../.gitbook/assets/image (13).png" alt="" width="375"><figcaption></figcaption></figure>

**Amount:** The number of tokens which will be progressively unlocked to the recipient

**Recipient Wallet Address:** The wallet address of the recipient, ensure the address is correct and you are connected to our platform on the correct chain.&#x20;

**Contract Title:** This is an optional title that can help the sender and recipient to identify what the contract relates to. This title is used in our platform as well as the email notification.&#x20;

**Recipient Email Address:** This is the email address where notifications about the contract will be sent including: contract start and each unlock.&#x20;

To add **multiple recipients**, click "+ Add Recipient" and then you can add the details the same way as the first recipient. We currently have a limit of up to 60-300 recipients (wallet dependent)  in one creation request. Note that each vesting contract will be visible separately after they are created.&#x20;

<figure><img src="../.gitbook/assets/image (14).png" alt="" width="375"><figcaption></figcaption></figure>

**Step 5: Review**

Next you'll land on the review page, where you can check the graph to confirm it matches your configuration expectations.

![](<../.gitbook/assets/image (4).png>)

Below you'll find some key details around the contract including:

1. Number of recipients
2. Total amount of tokens to be deployed to the contracts
3. Streamflow fees&#x20;

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Below the high level information you can find all the configuration information about the contract you've created as well as our fees once more.&#x20;

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

**Step 6: Create the contract**

Finally, click on the 'Create Payment Contract' button and approve the transaction in your wallet - congratulations, you've just created you're first contract on Streamflow.  &#x20;

<figure><img src="../.gitbook/assets/image (15).png" alt="" width="282"><figcaption></figcaption></figure>

**Email notifications**

If the recipient's email address has been added while creating the contract, an email will be sent to the given address with all the details about the vesting contract.

Additionally, the recipient gets notified when unlocked tokens are transferred into his/her wallet. Please keep in mind that adding the recipient's email address is an optional feature and it can only be added while creating the contract.

