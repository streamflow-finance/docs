# 💰 Using Realms (SPL Governance)

Streamflow is the leading platform for token vesting on the Solana network and it’s now integrated and available to handle streams on Realms.

This is a step-by-step walkthrough for creating a token vesting proposal on Realms using Streamflow’s integration.



**Step 1: Create a “New Proposal”**

![](../../.gitbook/assets/Xnip2022-08-11\_10-29-54.jpg)

Let’s start off by creating a “New Proposal”.



**Step 2: Select “Streamflow: Create Vesting Contract”**

From the dropdown menu select “Streamflow: Create Vesting Contract”

![](../../.gitbook/assets/Xnip2022-08-11\_10-30-58.jpg)

**Step 3: Complete the Transaction form**

![](../../.gitbook/assets/Xnip2022-08-11\_10-32-42.jpg)

**Token account:** Select the address with the SPL token that you need to stream (SRM in this case) 😀

**Recipient Address:** Input the recipient's wallet address

**Start:** This is the date that the stream will start. **IMPORTANT: Ensure that you provide sufficient time for the proposal to pass before the stream starts!**

**Amount:** This is the total NET amount that will be vested

**Released at start:** This is the amount that will release at the **Start** time.

**Release amount:** A stream progressively releases the tokens, the release amount refers to the amount unlocked per release

**Release frequency:** This input refers to the frequency that unlocks will take place.

**Release unit:** This gives you flexible control over the exact release rate.

**Note:** If you set Amount: 100 and release 10 at start you would have 90 remaining. If the release amount is 10 and the release frequency is 1 month, then the stream would be fully unlocked 9 months from initialization.

Additionally, please ensure that you have sufficient $SOL to pay for the transactions on the Multisig SOL account **as well as** the wallet address that is creating the proposal

****

**Step 4: Submit proposal**

We can see below the simulation is successful

![](<../../.gitbook/assets/Xnip2022-08-11\_11-32-46 (1).jpg>)

![](../../.gitbook/assets/Xnip2022-08-11\_11-33-27.jpg)



**Step 5: Viewing and Cancelling Stream after approval**

![](../../.gitbook/assets/Xnip2022-08-11\_11-47-37.jpg)

Once the stream has been approved, view the details of the stream by expanding the “instructions”. See the details of the stream as well as the current amount unlocked.

**Cancel:** To cancel the stream just click cancel and submit the tx. On success, a proposal to cancel the stream is created. On approval of the proposal the stream is cancelled from the moment the proposal passes (this can be mid stream).











