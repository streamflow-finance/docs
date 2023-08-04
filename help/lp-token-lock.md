# 🔓 LP Token Lock

Easily establish Token Locks to gate access to funds until a later date, helping to build trust with the community and safeguard against potential scams and rug pulls.

### What is a Token Lock?

Token locks require users to send tokens to a smart contract, where the tokens become inaccessible for trading or withdrawal. The tokens are held within the contract until the predetermined time period set by the token sender is fulfilled, at which point they are released.

Token-locks are most often used to lock liquidity pool (LP) tokens —from your project's liquidity allocation— for a fixed amount of time. Liquidity Pool (LP) Tokens are a type of receipt token representing ownership of a portion of liquidity within a decentralized exchange’s (DEXs) liquidity pool. When you list a token on a decentralized exchange (DEX) or deposit an existing token pair, you will receive what is known as 'LP Tokens.’

<figure><img src="../.gitbook/assets/Screen Shot 2023-08-02 at 12.12.36 PM.png" alt=""><figcaption></figcaption></figure>

stSOL/USDC LP tokens from Raydium DEX on Solana

Locking LP tokens prevents depositors of the liquidity from withdrawing their funds. It guarantees the community that liquidity will remain within the DEX to facilitate swaps, and not be cashed out by developers or project founders (like we’ve recently witnessed with [the launch of $BALD token on Base Network](https://cointelegraph.com/news/bald-token-developer-denies-rug-pull-price-falls-post-launch)). The locked LP tokens can only be withdrawn or changed at the end of the locked period(s).

### How to lock LPs with Streamflow?

To lock tokens, visit [Streamflow](https://app.streamflow.finance). You can lock virtually any token including NFTs, using our Token-lock feature.

_Note: To lock LPs, You must provide liquidity for your token pairing or an existing token pair on a DEX (to receive LP tokens), before locking with Streamflow._

#### Create Token Lock

1. Connect your wallet to Streamflow
2. Click **‘create new’,** to set up a new token lock
3. Choose the **token**
4. Set a **time & date** for the tokens to unlock
5.  Set the **amount** of funds you’d like to unlock, to your wallet

    Note: If you’re locking funds for other wallets, toggle **‘I am the recipient’** off\*\*,\*\* to enter other wallets
6. Click ‘**create lock**’ to lock tokens

### FAQ

**How do I create an LP token?**

To create an LP token, you'll need to list your token on a decentralized exchange and/or provide liquidity for an existing pair and create LP tokens.

**How long should I lock liquidity (LP tokens) for?**

The length of time-locks depends on your project's needs, but a general rule, is the longer the lockup the better.

**How much of my liquidity should I lock?**

Teams often lock the tokens earmarked for their liquidity allocation. However, you can lock multiple allocations depending on your project's needs.

**How do I withdraw tokens once my lock ends?**

When you’re token-lock has expired, it will be ‘unlocked’ and automatically withdrawn to the recipient's wallet.

**How do I upload multiple recipients at once?**

To load multiple recipients at once, download our CSV template and enter your recipient information. Upload the newly edited CSV to Streamflow to load recipients.
