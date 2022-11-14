# Troubleshooting Errors

![](.gitbook/assets/help.png)

Sometimes you may find yourself facing a problem that doesn't have a clear solution. These troubleshooting tips may help you solve problems you run into.

### **Issues on the Exchange**

#### **INSUFFICIENT\_OUTPUT\_AMOUNT**

> The transaction cannot succeed due to error: MoonwalkerRouter: INSUFFICIENT\_OUTPUT\_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: moonwalkerrouter: insufficient\_output\_amount.

You're trying to swap tokens, but your slippage tolerance is too low or liquidity is too low.

{% tabs %}
{% tab title="Solution" %}
1. Refresh your page and try again later.
2. Try trading a smaller amount at one time.
3. Increase your slippage tolerance:
   1. Tap the settings icon on the liquidity page.
   2. Increase your slippage tolerance a little and try again.&#x20;
4. Lastly, try inputting an amount with fewer decimal places.
{% endtab %}

{% tab title="Reason 1" %}
**This usually happens when trading tokens with low liquidity.**
{% endtab %}

{% tab title="Reason 2" %}
That means there isn't enough of one of the tokens you're trying to swap in the Liquidity Pool: it's probably a small-cap token that few people are trading.
{% endtab %}

{% tab title="Reason 3" %}
However, there's also the chance that you're trying to trade a scam token which cannot be sold. In this case, MoonwalkerSwap isn't able to block a token or return funds.
{% endtab %}

{% tab title="Reason 4" %}
#### **INSUFFICIENT\_A\_AMOUNT or INSUFFICIENT\_B\_AMOUNT**
{% endtab %}

{% tab title="Reason 5" %}
> Fail with error 'MoonwalkerRouter: INSUFFICIENT\_A\_AMOUNT'\
> or\
> Fail with error 'MoonwalkerRouter: INSUFFICIENT\_B\_AMOUNT'
{% endtab %}

{% tab title="Reason 6" %}
You're trying to add/remove liquidity from a liquidity pool (LP), but there isn't enough of one of the two tokens in the pair.
{% endtab %}

{% tab title="Reason 7" %}
**Refresh your page and try again, or try again later.**
{% endtab %}

{% tab title="" %}
Still doesn't work?
{% endtab %}

{% tab title="undefined" %}
1. Tap the settings cog icon on the liquidity page.
2. Increase your slippage tolerance a little and try again.
{% endtab %}

{% tab title="undefined" %}
The error is caused by trying to add or remove liquidity for a liquidity pool (LP) with an insufficient amount of token A or token B (one of the tokens in the pair).
{% endtab %}

{% tab title="undefined" %}
It might be the case that prices are updating too fast when and your slippage tolerance is too low.
{% endtab %}

{% tab title="Solution for nerds" %}
OK, so you're really determined to fix this. We really don't recommend doing this unless you know what you're doing.

There currently isn't a simple way to solve this issue from the PancakeSwap website: you'll need to interact with the contract directly. You can add liquidity directly via the Router contract, while setting amountAMin to a small amount, then withdrawing all liquidity.

#### **Approve the LP contract**

Head to the contract of the LP token you're trying to approve.\
For example, here's the ETH/WBNB pair: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Select **Write Contract**, then **Connect to Web3** and connect your wallet. ![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
2. In **section "1. approve",** approve the LP token for the router by entering
   1. spender (address): enter the contract address of the LP token you're trying to interact with
   2. value (uint256): -1

#### Query "balanceOf"

1. Switch to **Read Contract.**
2. In **5. balanceOf**, input your wallet address and hit **Query**.
3. Keep track of the number that's exported. It shows your balance within the LP in the uint256 format, which you'll need in the next step.

#### Add or Remove Liquidity

Head to the router contract: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Select **Write Contract** and **Connect to Web3** as above.
2. Find **addLiquidity** or **removeLiquidity** (whichever one you're trying to do)
3. Enter the token addresses of both of the tokens in the LP.
4. In **liquidity (uint256),** enter the uint256 number which you got from "balanceOf" above.
5. Set a low **amountAMin** or **amountBMin**: try 1 for both.
6. Add your wallet address in **to (address)**.
7. Deadline must be an epoch time greater than the time the tx is executed.

{% hint style="warning" %}
This can cause very high slippage, and can cause the user to lose some funds if frontrun
{% endhint %}
{% endtab %}
{% endtabs %}

#### MoonwalkerRouter: EXPIRED

> The transaction cannot succeed due to error: MoonwalkerRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Try again, but confirm (sign and broadcast) the transaction as soon as you generate it.

This happened because you started making a transaction, but you didn't sign and broadcast it until it was past the deadline. That means you didn't hit "Confirm" quickly enough.

#### Moonwalker: K

> The transaction cannot succeed due to error: Moonwalker: K. This is probably an issue with one of the tokens you are swapping.

Try modifying the amount on “To” field. Therefore putting "(estimated)" symbol on “From”. Then initiate the swap immediately.

This usually happen when you are trying to swap a token with its own fee.

#### Moonwalker: TRANSFER\_FAILED

> The transaction cannot succeed due to error: execution reverted: Moonwalker: TRANSFER\_FAILED.

Make sure you have 30% more tokens in your wallet than you intend to trade, or try to trade a lower amount. If you want to sell the maximum possible, try 70% or 69% instead of 100%.\
Caused by the design of Restorative Rebase tokens like tDoge or tBTC.\
[Understand how restorative rebase tokens work](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Another possible cause of this issue is the malicious token issuer just suspended the trading for their token. Or they made selling action only possible for selected wallet addresses. Please always do your own research to avoid any potential fraud. If the token you are trying to swap but failed with this error code is coming from an airdrop, that is most likely a scam. Please do not perform any token approval or follow any links, your fund may be at risk if you try to do so.

#### Transaction cannot succeed

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

#### **Price Impact too High**

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

#### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Solution" %}
**If you got this error while removing liquidity from a BNB pair:**

Please select "Receive WBNB" and retry.

**If you got this error while trying to swap:**

Please contact the project team of the token you're trying to swap. _\*\*_This issue must be resolved by the project team.
{% endtab %}

{% tab title="Reason" %}
**This issue (while swapping) is caused by tokens which have hard-coded MoonwalkerSwap router into their contract.**

While this practice is ill-advised at best, the reason for these projects having done this appears to be due to their tokenomics, in which each purchase sends a % of the token to LPs.

The projects affected will likely not work with the V2 router: they will most likely need to create new versions of their tokens pointing to our new router address, and migrate any existing token holders to their new token.

We recommend that any projects which created such tokens should also make efforts to prevent their users from adding them to LP.

The up-to-date router address is [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

#### Cannot read property 'toHexString' of undefined

> "Unknown error: "Cannot read property 'toHexString' of undefined"

When trying to swap tokens, the transaction fails and this error message is displayed. This error has been reported on mobile devices using Trust Wallet.

{% tabs %}
{% tab title="Solution" %}
1. Attempt the transaction again with increased slippage allowance.
2. If 1. does not resolve your problem, consider using another wallet such as SafePal for your transaction.
{% endtab %}

{% tab title="Reason" %}
**This usually happens when trading tokens with insufficient slippage allowance on Trust Wallet.**

The exact details of the problem are still being investigated.
{% endtab %}
{% endtabs %}

#### **Execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER\_FROM\_FAILED.

When trying to swap tokens, the transaction fails and this error message is displayed. This error has been reported across platforms.

{% tabs %}
{% tab title="Solution" %}
1. Check to make sure you have sufficient funds available.
2. Ensure you have given the contract allowance to spend the amount of funds you're attempting to trade with.
{% endtab %}

{% tab title="Reason" %}
This error happens when trading tokens with insufficient allowance, or when a wallet has insufficient funds.\
If you're trading tokens with Restorative Rebase like tau assets tDoge or tBTC, make sure you understand how they work first with this [guide to Rebase tokens](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).
{% endtab %}
{% endtabs %}

### **Issues with Space Pools**

#### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

You don't have enough SpaceBar in your wallet to unstake from the DUST-DUST pool.

**Get at least as much SPACEBAR as the amount of DUST that you’re trying to unstake.**

1. Buy SPACEBAR on the exchange. If you want to unstake 100 DUST, you need at least 100 SPACEBAR.
2. Try unstaking again.

If that still fails, you can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Go to: [https://bscscan.com/address/0x34c3deb04f6f30fdd8f2eaa52d41b08c2dcb9ae1#writeContract ](https://bscscan.com/address/0x34c3deb04f6f30fdd8f2eaa52d41b08c2dcb9ae1#writeContract)
2. Click **“Connect to Web3”** and connect your wallet.
3. In section **“4. emergencyWithdraw”**, enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected DUST yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}



To stop this happening again, **don’t sell your SPACEBAR.** You still need it to unstake from the “Stake DUST Earn DUST” pool.

This error has happened because you have sold or transferred SPACEBAR tokens. SPACEBAR is minted in a 1:1 ratio to DUST when you stake in the DUST-DUST Space Pool. SPACEBAR must be burned at a 1:1 ratio to DUST when calling leaveStaking (unstaking your DUST from the pool), so if you don't have enough, you can't unstake from the pool.

#### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]

You have set a low gas limit when trying to make a transaction.

{% tabs %}
{% tab title="Solution" %}
Try manually increasing the **gas limit** (not gas price!) in your wallet before signing the transaction.

A limit of 200000 is usually enough.
{% endtab %}

{% tab title="Reason" %}
Basically, your wallet (Metamask, Trust Wallet, etc.) can't finish what it's trying to do.

Your wallet estimates that the gas limit is too low, so the function call runs out of gas before the function call is finished.
{% endtab %}
{% endtabs %}

#### BEP20: transfer amount exceeds allowance

> Fail with error 'BEP20: transfer amount exceeds allowance'

{% tabs %}
{% tab title="Solution" %}
1. Use Unrekt.net to revoke approval for the smart contract you're trying to interact with
2. Approve the contract again, without setting a limit on spend allowance
3. Try interacting with the contract again.
{% endtab %}

{% tab title="Reason" %}
This happens when you set a limit on your spend allowance when you first approved the contract, then try to swap more than the limit.
{% endtab %}
{% endtabs %}

#### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

You're probably trying to unstake from a Space Pool with low rewards in it. Solution below.

If not, you may be trying to send tokens that you don't have in your wallet (for example, trying to send a token that is already assigned to a pending transaction). In this case, just make sure you have the tokens you're trying to use.

{% tabs %}
{% tab title="Solution" %}
Firstly, [let the team](https://discord.gg/RSRMJsvp) know which pool you're trying to unstake from, so they can top up the rewards. If you're in a hurry to unstake and you don't mind losing your pending yield, try an emergencyWithdraw:

You can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Find the contract address of the Syrup Pool you're trying to unstake from. You can find it in your wallet's transaction log.
2. Go to [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) and in the search bar, enter the contract address.
3. Select **Write Contract.**
4. Click **“Connect to Web3”** and connect your wallet.![](https://lh6.googleusercontent.com/-\_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk\_1dTHkPuCmE50vpNNZxEqoM5nPmE\_12k3-8Q8YYoRYqJ\_VGjxJ03YPRuVQ1O5ME)
5. In section **“4. emergencyWithdraw”,** enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}
{% endtab %}

{% tab title="Reason" %}
This error tends to appear when you're trying to unstake from an old Syrup Pool, but there aren't enough rewards in the pool left for you to harvest when withdrawing. This causes the transaction to fail.
{% endtab %}
{% endtabs %}

### **Other issues**

#### Provider Error

> Provider Error\
> No provider was found

This happens when you try to connect via a browser extension like MetaMask or Binance Chain Wallet, but you haven’t installed the extension.

{% tabs %}
{% tab title="Solution" %}
Install the official browser extension to connect, or read our guide on [how to connect a wallet to MoonwalkerSwap.](guides.md#how-to-use-metamask-on-moonwalkerswap)
{% endtab %}
{% endtabs %}

#### Unsupported Chain ID

Switch your chain to Binance Smart Chain. Check your wallet's documentation for a guide if you need help.

#### Issues buying SAFEMOON and similar tokens

To trade SAFEMOON, you must click on the settings icon and **set your slippage tolerance to 12% or more.**\
This is because **SafeMoon taxes a 10% fee on each transaction**:

* 5% fee = redistributed to all existing holders
* 5% fee = used to add liquidity

This is also why you might not receive as much of the token as you expect when you purchase.

#### Internal JSON-RPC errors

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Happens when trying to remove liquidity on some tokens via Metamask. Root cause is still unknown. Try using an alternative wallet.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

You don't have enough BNB to pay for the transaction fees. You need more BEP-20 network BNB in your wallet.

#### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Increase the gas limit for the transaction in your wallet. Check your wallet's documentation to learn how to increase gas limit.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Cause unclear. Try these steps before trying again:

1. Increase gas limit
2. Increase slippage
3. Clear cache

## Fixing Stuck Pending Transactions on MetaMask

If your transaction is stuck on pending in Metamask, and the “Cancel” button isn’t helping, you might need to use this method to clear your backlog.

This method works by essentially overwriting the stuck transaction with another, higher-priority transaction.

#### **1. Enable Customized Transaction Nonce**

1. Open your MetaMask plugin.
2. Click on the colourful circle icon on the top-right and click **Settings** from the dropdown menu.
3. In the Settings menu, select **Advanced**.
4. Scroll down until you see **Advanced gas controls**. Toggle this to ON.
5. Still in Advanced settings, keep scrolling until you see **Customize transaction nonce**. Toggle this to ON.

#### **2. Find Your Stuck Transaction**

We’re now going to find the transaction that’s stuck, and make a note of the “nonce”. That’s a kind of identifier, which we’ll re-use later.

1. Go back to the top page of MetaMask. In the “Assets” tab, find the token type of your stuck transaction (in this case, DUST).
2. In the token’s menu, find your **Pending** transaction in the Queue area. Click on your transaction for more details.
3. Look for the **Nonce** entry, and take note of this number.

#### **3. Overwrite the Stuck Transaction**

Now we’re going to make a new transaction to replace the stuck one. We’ll customize the Nonce number, so that it’s the same as the one that you just wrote down.

1. Create a new transaction to replace your stuck transaction. This time around, increase the **Transaction Fee**. Here we’ve increased it from 9 to 20. This will make it more likely for  your transaction to be added to a block.
2. On the confirmation page, make sure your Gas Price is now at your new, higher amount.
3. Find the **CUSTOM NONCE** entry and change the nonce to the number you wrote down in step 7. Now click Confirm.
4. Your new transaction should now be accepted into a block. To check, open MetaMask and click the **Activity** tab.
5. Your completed transaction should show at the top of your Activity list. If it still says “Pending” in orange you’ll need to wait a little longer, or try the process again with an even higher transaction fee (gas price).

Since no wallet can create two transactions of the same nonce, if the replacement transaction you make is successful, your stuck transaction will be canceled.
