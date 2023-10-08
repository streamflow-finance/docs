---
description: >-
  Following video walks you through complete process for creating vesting
  contracts on Ethereum mainnet, BNB Chain, Polygon, Solana, Aptos and Sui
  network.
---

# 💰 Create a Vesting contract

{% embed url="https://www.loom.com/share/614e86c2919b440f8b5f77e987643abb?sid=c8e4c13a-5111-436f-913e-ee0dfa78c751" %}
Streamflow token vesting
{% endembed %}

\
**Text tutorial:**\
\
Let’s go through a step-by-step process of creating token vesting contracts using Streamflow.

#### Step 1: Connect the wallet

Firstly, you need to visit the Streamflow app via the following URL:

👉 [app.streamflow.finance](https://bit.ly/3igHaDj)

Next, you will have to connect the wallet to start using the app. We support majority of wallets on Ethereum mainnet, BNB Chain, Polygon, Solana, Aptos and Sui network.

\
**Step 2:** **Select the token, release frequency, and vesting duration**

Select the token of your choice that you want to vest from the drop-down list of the Solana/Aptos tokens available in your wallet. You will also be able to see the token balance.

Next, you need to select the **release frequency** that can be chosen in the form of different time units, such as second, minute, hour, day, week, month, and year. A proportional amount of the vested tokens will be released in accordance with release frequency.

The duration of the vesting contract is an important parameter, you can choose the start date/time and end date/time of the vesting contract from the respective tabs.

![](<../../.gitbook/assets/Screenshot 2023-01-03 at 19.04.04.png>)\
\
**Step 3:** **Cliff time release and cancel/transfer permission**

By using the cliff time release feature, a certain percentage of the total vested tokens can be released with the first flow/unlock of the vested funds.\
\
For example, if you set the cliff time release at 10%, ten percent of the total vested tokens will be released as soon as the vesting contract starts streaming tokens, and the recipient will immediately be able to withdraw those unlocked tokens. \*\*\*\* The remaining vested amount will be streamed at a constant rate for the rest of the vesting duration.\
\*\*\*\*\
\*\*\*\*Let’s say you create a vesting contract with a total amount of 50 USDC tokens using a cliff release of 10 percent.

This means that 5 USDC (10% OF 50 USDC) will get unlocked as soon as the vesting contract starts streaming, and the remaining vested amount (45 USDC) will be streamed at a constant rate (in accordance with the release frequency) for the rest of the vesting duration.

**Moving on to cancel/transfer permissions**, you can choose who gets the authority to cancel or \*\*\*\* transfer \*\*\*\* the vesting contract from the sender/recipient. Please grant these permissions carefully because you can not change cancel and transfer permissions once a contract has gone live.

![](<../../.gitbook/assets/Screenshot 2023-01-03 at 18.58.48 (1).png>)

\
**Step 4: Adding recipient(s) with vesting amount, contract title, and email address (Manually)**

The Streamflow app supports the creation of vesting contracts in bulk, in other words, you can add as many recipients as you need with the vesting amounts of your choice for each recipient. You can also add the title of the contract for each recipient along with the (optional) email address.

Enter the total number of tokens to be vested into the amount tab, and the subject of the vesting contract can be typed in the contract title tab. The wallet address of the recipient can be pasted in the given field.

Optionally, you can also add the recipient's email address, and an email is sent to the recipient regarding the creation of the vesting contract. The recipient also gets notified when unlocked tokens are transferred into the wallet.

You will get an option on the bottom left to add more recipients in order to create vesting contracts in bulk. Please remember that the cliff release percentage and the contract duration will be the same for all the recipients.

![Adding recipients manually](<../../.gitbook/assets/Mr Alex vesting contrcat.png>)

![Adding more recipients](<../../.gitbook/assets/Mr Bob.png>)

\
**CSV Upload: Import recipient addresses, token amounts, contract titles, and optional email addresses directly from a CSV file**\
\
Alternatively, if you are looking to set up vesting contracts for many recipients, you can alternatively make use of our CSV upload feature.

![Click on CSV UPLOAD](<../../.gitbook/assets/Click here to import spreasheet (1).png>)

Next, just select the CSV file and click on the upload button. The wallet addresses of all the recipients will be imported automatically from the CSV file along with token amounts, contract titles, and optional email addresses.

![Select the CSV file and click on ''Upload'' button](<../../.gitbook/assets/Untitled design (89).png>)

Just make sure that each row matches the following format:

![Format of CSV spreadsheet](<../../.gitbook/assets/Untitled design (88).png>)

\
**Step 5: Automatic claim, referral address, and overview**

Automatic claim is a quite useful feature, it automatically transfers the unlocked tokens into the recipient’s wallet at the set frequency. It is not compulsory to enable auto-withdrawal, the recipient can also connect the wallet to the Streamflow app and manually withdraw the unlocked funds by interacting with the incoming vesting contract stream.

In case someone referred you to Streamflow token vesting, just paste the wallet address of the referrer into the referral address tab. A decent portion of the service fees will be sent to the referral address as a reward.

![Automatic claim](<../../.gitbook/assets/streaming auto withdrawal shot (1) (1).png>)

![Referral address](<../../.gitbook/assets/ref address] (1).JPG>)

Finally, take a look at the overview tab to see all the parameters of your vesting contracts, click on the 'create vesting contract' button, and approve the transaction in your wallet. Your vesting contracts will go live on the Solana network/Aptos network as soon as the transaction is confirmed.\
\
Please note that if you have added the recipient's email address, you will get an additional wallet pop-up to sign the message. In other words, it is simply an approval for sending email notifications.

![Overview of the parameters of the vesting contracts](<../../.gitbook/assets/Untitled design (82).png>)

<figure><img src="../../.gitbook/assets/Screenshot 2023-01-03 at 19.08.09.png" alt=""><figcaption><p>Click on this button to create stream</p></figcaption></figure>

Once the transaction is confirmed on the Solana network/Aptos network, you will be able to see the vesting contracts on the 'outgoing streams' page. You can expand the view of each vesting contract to see all the details and to interact with the vesting contract.

![Outgoing vesting contract streams](<../../.gitbook/assets/Untitled design (83) (1).png>)

#### Email notifications

If the recipient's email address has been added while creating the contract, an email will be sent to the given address with all the details about the vesting contract.

![Each recipient receives an email notification when the vesting contract is created](<../../.gitbook/assets/Untitled design (84).png>)

Additionally, the recipient gets notified when unlocked tokens are transferred into his/her wallet. Please keep in mind that adding the recipient's email address is an optional feature and it can only be added while creating the contract.

#### Managing live vesting contracts

The sender will be able to see and interact with the vesting contracts on the 'outgoing streams' page. Please keep in mind that you will have to click on the three dots (...) right below the 'actions' heading to see the options to interact with the stream.

![Full view of an outgoing vesting contract stream](<../../.gitbook/assets/Untitled design (85).png>)

Depending on the permissions granted while creating the vesting contract, the sender might also get the option to cancel or transfer the stream.

The recipient will be able to see and interact with the vesting contract on the 'incoming streams' page. As a recipient, you will get the option to withdraw the unlocked amount at any point in time. Depending on the permissions granted while creating the vesting contract, the recipient might also get the option to cancel or transfer the stream.

![Full view of an incoming vesting contract stream](<../../.gitbook/assets/incoming stream view batch.png>)

#### How to manually withdraw the unlocked amount

The recipient can manually withdraw the unlocked tokens into his/her wallet at any point in time, just click on the withdraw button, select the amount, and approve the transaction.

In case auto-withdrawal has been enabled by the sender while creating the contract, the recipient will not need to connect the wallet to the Streamflow app to manually withdraw the unlocked funds from the vesting contract.

![Manual withdrawal](<../../.gitbook/assets/withdraw batch.png>)

#### How to transfer a vesting contract

Depending on the permissions granted while creating the vesting contract, the sender/recipient might get an option to transfer the contract. Just click on the transfer button, enter the new wallet address for the recipient, and approve the transaction. The transfer option can be useful both for changing the wallet address of the existing recipient or transferring the contract to a completely new recipient.\
\
When a vesting contract is transferred, the contract gets transferred to the new address with both the locked amount as well as the unlocked amount of tokens that have not been withdrawn by the previous recipient.

![New wallet address of the recpient can be entered into the address field](<../../.gitbook/assets/transfer (1).png>)

#### How to cancel a vesting contract

Depending on the permissions granted while creating the vesting contract, the sender/recipient might get an option to cancel the contract.\
\
When a vesting contract is canceled, the amount that has not been unlocked yet is returned to the sender, whereas the unlocked amount is automatically withdrawn into the recipient's wallet.

![View of a canceled vesting contract](<../../.gitbook/assets/cancelted stream view batch.png>)

**Conclusion**\
\
You are now all set to set up token vesting contracts using Streamflow dApp. In case you get stuck at any point, feel free to reach out to us in Streamflow discord.

