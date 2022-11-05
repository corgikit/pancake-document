---
description: Common error messages. Use the sidebar ➡️to jump to the error you're seeing.
---

# Troubleshooting Errors

![](../.gitbook/images/troubleshooting-header.png)

You may occasionally encounter an issue for which there is no obvious answer. These troubleshooting suggestions may assist you in resolving issues.

## **Issues on the Exchange**

### **INSUFFICIENT_OUTPUT_AMOUNT**

> The transaction cannot succeed due to error: ZexdexRouter: INSUFFICIENT_OUTPUT_AMOUNT. This is probably an issue with one of the tokens you are swapping.
>
> the transaction cannot succeed due to error: execution reverted: ZexdexRouter: insufficient_output_amount.

You're trying to swap tokens, but your slippage tolerance is too low or liquidity is too low.

{% tabs %}
{% tab title="Solution" %}

1. Refresh your page and try again later.
2. Try trading a smaller amount at one time.
3. Increase your slippage tolerance:
   1. Tap the settings icon on the liquidity page.
   2. Increase your slippage tolerance a little and try again. ![](<../.gitbook/images/image (9) (4) (2) (1) (1) (1) (1) (1) (1) (1) (3).png>)
4. Lastly, try inputting an amount with fewer decimal places.

{% endtab %}
{% tab title="Reason" %}
**This usually happens when trading tokens with low liquidity.**

That signals that one of the tokens you're attempting to swap doesn't have adequate liquidity in the Liquidity Pool: it's most likely a small-cap token with few traders.

However, there is a chance that you are exchanging a fraudulent token that cannot be exchanged. In this case, ZexdexApp is unable to prohibit a token or reimburse money.

{% endtab %}
{% endtabs %}

### **INSUFFICIENT_A_AMOUNT or INSUFFICIENT_B_AMOUNT**

> Fail with error 'ZexdexRouter: INSUFFICIENT_A_AMOUNT'\
> or\
> Fail with error 'ZexdexRouter: INSUFFICIENT_B_AMOUNT'

You're trying to add/remove liquidity from a liquidity pool (LP), but there isn't enough of one of the two tokens in the pair.

{% tabs %}
{% tab title="Solution" %}
**Refresh your page and try again, or try again later.**

Still doesn't work?

1. Tap the settings icon on the liquidity page.
2. Increase your slippage tolerance a little and try again.

![](<../.gitbook/images/image (9) (4) (2) (1) (1) (1) (1) (1) (1) (1) (4).png>)
{% endtab %}

{% tab title="Reason" %}
The error occurs while attempting to add or withdraw liquidity from a liquidity pool (LP) with insufficient token A or token B. (one of the tokens in the pair).

It is possible that prices are updating too quickly and your slippage tolerance is too low.

![](https://lh5.googleusercontent.com/T1KMtz2ILDVHljGw1iLbIv0W1KVl7qXL8zU2nLFHkUvDb5oMw9mpUzzBwWmIBz15XDsxZ5w7wsaqAwCs_pxdobz_kY_7BhcZhYtpqWuQGFs23DZq98-SVInlfsS07WzxFPLIYXHt)

![](https://lh5.googleusercontent.com/7aspaCCvDjzxbJxngqwgeq737LB3OUNcAs592QqlEkyrAOTfKsrt_FAwpEylaIJhff5ZcYlzB_r0v1JZwfj3j8Ah6jlUbRoMrAqVfTb3cwDI7B1i5HJtZSQOsTPrv7l7SaclC3BV)
{% endtab %}

{% tab title="Solution for nerds" %}
So you're dead set on resolving this. We strongly advise against doing this unless you are confident in your abilities.

There is presently no easy method to remedy this problem through the ZexdexApp website: you must deal with the contract directly. You may immediately add liquidity via the Router contract by setting amountAMin to a tiny amount and then withdrawing all liquidity.

#### **Approve the LP contract**

Head to the contract of the LP token you're trying to approve.\
For example, here's the ETH/WBNB pair: [https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422](https://bscscan.com/address/0x70d8929d04b60af4fb9b58713ebcf18765ade422)

1. Select **Write Contract**, then **Connect to Web3** and connect your wallet. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
2. In **section "1. approve",** approve the LP token for the router by entering
   1. spender (address): enter the contract address of the LP token you're trying to interact with
   2. value (uint256): -1

#### Query "balanceOf"

1. Switch to **Read Contract.**
2. In **5. balanceOf**, input your wallet address and hit **Query**.
3. Keep track of the number that's exported. It shows your balance within the LP in the uint256 format, which you'll need in the next step.

![](<../.gitbook/images/image (7) (1).png>)

#### Add or Remove Liquidity

Head to the router contract: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#writeContract)

1. Select **Write Contract** and **Connect to Web3** as above.
2. Find **addLiquidity** or **removeLiquidity** (whichever one you're trying to do)
3. Enter the token addresses of both of the tokens in the LP.
4. In **liquidity (uint256),** enter the uint256 number which you got from "balanceOf" above.
5. Set a low **amountAMin** or **amountBMin**: try 1 for both.
6. Add your wallet address in **to (address)**.
7. Deadline must be an epoch time greater than the time the tx is executed.

![](<../.gitbook/images/image (5) (1).png>)

{% hint style="warning" %}
This can cause very high slippage, and can cause the user to lose some funds if frontrun
{% endhint %}
{% endtab %}
{% endtabs %}

### ZexdexRouter: EXPIRED

> The transaction cannot succeed due to error: ZexdexRouter: EXPIRED. This is probably an issue with one of the tokens you are swapping.

Retry, but this time confirm (sign and broadcast) the transaction as soon as it is generated.

This occurred because you began a transaction but did not sign or broadcast it until it was past the deadline. That indicates you didn't press "Confirm" fast enough.

### Zexdex: K

> The transaction cannot succeed due to error: Zexdex: K. This is probably an issue with one of the tokens you are swapping.

Change the amount in the "To" field. As a result, the "(estimated)" sign is placed on "From." Then immediately begin the exchange.

![](../.gitbook/images/zexdex-k-solution.png)

This commonly happens when you try to exchange a token with its own charge.

### Zexdex: TRANSFER_FAILED

> The transaction cannot succeed due to error: execution reverted: Zexdex: TRANSFER_FAILED.

Make sure you have 30% more tokens in your wallet than you want to trade, or trade less. If you want to sell the most, attempt 70% or 69% rather than 100%.
Because of the design of Restorative Rebase tokens like as tDoge and tBTC.
[Understand how restorative rebase tokens work](https://btcst.medium.com/stp-8-restorative-rebase-b4fbbdfd96c).

Another possibility is that the fraudulent token creator has simply ceased trade for their token. Or they limited the ability to sell to specific wallet addresses. To avoid any fraud, always always conduct your own research. If the token you're attempting to exchange but failing with this error code came from an airdrop, it's most likely a fraud. Please do not approve any tokens or click on any links, your fund may be at risk if you try to do so.

### Transaction cannot succeed

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

### **Price Impact too High**

Try trading a smaller amount, or increase slippage tolerance via the settings icon and try again. This is caused by low liquidity.

### estimateGas failed

> This transaction would fail. Please contact support

{% tabs %}
{% tab title="Solution" %}
**If you got this error while removing liquidity from a BNB pair:**

Please select "Receive WBNB" and retry.

**If you got this error while trying to swap:**

Please contact the project team of the token you're trying to swap. \*\*\*\* This issue must be resolved by the project team.
{% endtab %}

{% tab title="Reason" %}
**This issue (while swapping) is caused by tokens which have hard-coded into their contract.**

While this is an unwise practice at best, the reason these companies have done so appears to be owing to their tokenomics, in which each purchase distributes a percentage of the token to LPs.

The impacted projects will very likely not be able to use the V2 router: they will need to generate new versions of their tokens that link to our new router address, as well as convert any existing token holders to their new token.

We advise any projects that produced such tokens to make attempts to prevent their users from adding them to the latest LP.

The up-to-date router address is [https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E](https://bscscan.com/address/0x10ED43C718714eb63d5aA57B78B54704E256024E)
{% endtab %}
{% endtabs %}

### Cannot read property 'toHexString' of undefined

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

### **Execution reverted: TransferHelper: TRANSFER_FROM_FAILED.**

> The transaction cannot succeed due to error: execution reverted: TransferHelper: TRANSFER_FROM_FAILED.

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

## **Issues with Staking Pools**

### BEP20: burn amount exceeds balance

> Fail with error 'BEP20: burn amount exceeds balance'

You don't have enough sDEX in your wallet to unstake from the zDEX-zDEX pool.

**Get at least as much sDEX as the amount of zDEX that you’re trying to unstake.**

1. Buy sDEX on the exchange. If you want to unstake 100 zDEX, you need at least 100 sDEX.
2. Try unstaking again.

If that still fails, you can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Go to: [https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract)
2. Click **“Connect to Web3”** and connect your wallet. ![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
3. In section **“4. emergencyWithdraw”**, enter "0" and click “Write”.

This will unstake your staked tokens and lose any uncollected zDEX yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}

To stop this happening again, **don’t sell your sDEX.** You still need it to unstake from the “Stake zDEX Earn zDEX” pool.

This error has happened because you have sold or transferred sDEX tokens. sDEX is minted in a 1:1 ratio to zDEX when you stake in the zDEX-zDEX Staking Pool. sDEX must be burned at a 1:1 ratio to zDEX when calling leaveStaking (unstaking your zDEX from the pool), so if you don't have enough, you can't unstake from the pool.

{% embed url="https://dashboard.tenderly.co/tx/binance/0x754e18ceea82acac256b49c2b7a81260f7f86dd5e56ee2e3cc1b6ac864c29a8e" %}

### Out of Gas error

> Warning! Error encountered during contract execution \[out of gas]

You have set a low gas limit when trying to make a transaction.

{% tabs %}
{% tab title="Solution" %}
Try manually increasing the **gas limit** (not gas price!) in your wallet before signing the transaction.

A limit of 200000 is usually enough.

![](<../.gitbook/images/image (2) (1) (1).png>)

The above example is from Metamask; check your wallet's documentation if you aren't sure how to adjust the gas limit.
{% endtab %}

{% tab title="Reason" %}
Basically, your wallet (Metamask, Trust Wallet, etc.) can't finish what it's trying to do.

Your wallet estimates that the gas limit is too low, so the function call runs out of gas before the function call is finished.
{% endtab %}
{% endtabs %}

### BEP20: transfer amount exceeds allowance

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

### BEP20: transfer amount exceeds balance

> Fail with error 'BEP20: transfer amount exceeds balance'

You're probably trying to unstake from a Staking Pool with low rewards in it. Solution below.

If not, you may be trying to send tokens that you don't have in your wallet (for example, trying to send a token that is already assigned to a pending transaction). In this case, just make sure you have the tokens you're trying to use.

{% tabs %}
{% tab title="Solution" %}
Firstly, [let the team know](../contact-us/socials-communities.md) which pool you're trying to unstake from, so they can top up the rewards. If you're in a hurry to unstake and you don't mind losing your pending yield, try an emergencyWithdraw:

You can perform an “emergencyWithdraw” from the contract directly to unstake your staked tokens.

1. Find the contract address of the Staking Pool you're trying to unstake from. You can find it in your wallet's transaction log.
2. Go to [https://bscscan.com/](https://bscscan.com/address/0x73feaa1eE314F8c655E354234017bE2193C9E24E#writeContract) and in the search bar, enter the contract address.
3. Select **Write Contract.**
4. Click **“Connect to Web3”** and connect your wallet.![](https://lh6.googleusercontent.com/-_sNkO1gcOOJXkduDEUzbExKE2mNxBOR0f86Lpp3BBuPbIcmAHsfuvpF-hKqRn4oID5QzdGkk_1dTHkPuCmE50vpNNZxEqoM5nPmE_12k3-8Q8YYoRYqJ_VGjxJ03YPRuVQ1O5ME)
5. In section **“3. emergencyWithdraw”,** and click “Write”.

This will unstake your staked tokens and lose any uncollected yield.

{% hint style="warning" %}
**This will lose any yield that you haven’t harvested yet.**
{% endhint %}
{% endtab %}

{% tab title="Reason" %}
This error tends to appear when you're trying to unstake from an old Staking Pool, but there aren't enough rewards in the pool left for you to harvest when withdrawing. This causes the transaction to fail.
{% endtab %}
{% endtabs %}

## **Issues with Zex Binary Option**

Check [zbo-troubleshooting.md](../products/zex-binary-option/zbo-troubleshooting.md "mention")

## **Other issues**

### Provider Error

> Provider Error\
> No provider was found

This happens when you try to connect via a browser extension like MetaMask or Binance Chain Wallet, but you haven’t installed the extension.

{% tabs %}
{% tab title="Solution" %}
Install the official browser extension to connect, or read our guide on [how to connect a wallet to ZexdexApp](../get-started/connection-guide).
{% endtab %}
{% endtabs %}

### Unsupported Chain ID

Switch your chain to BNB Smart Chain. Check your wallet's documentation for a guide if you need help.

### Already processing eth_requestAccounts. Please wait.

Make sure you are signed in to your wallet app and it's connected to BNB Smart Chain.

### Issues buying SAFEMOON and similar tokens

To trade SAFEMOON, you must click on the settings icon and **set your slippage tolerance to 12% or more.**\
This is because **SafeMoon taxes a 10% fee on each transaction**:

- 5% fee = redistributed to all existing holders
- 5% fee = used to add liquidity

This is also why you might not receive as much of the token as you expect when you purchase.\
Read more on [How to Buy Safe Moon](https://community.trustwallet.com/t/how-to-buy-safemoon/155742).

### Internal JSON-RPC errors

> "MetaMask - RPC Error: Internal JSON-RPC error. estimateGas failed removeLiquidityETHWithPermitSupportingFeeOnTransferTokens estimateGas failed removeLiquidityETHWithPermit "

Happens when trying to remove liquidity on some tokens via Metamask. Root cause is still unknown. Try using an alternative wallet.

> Internal JSON-RPC error. { "code": -32000, "message": "insufficient funds for transfer" } - Please try again.

You don't have enough BNB to pay for the transaction fees. You need more BEP-20 network BNB in your wallet.

### Error: \[ethjs-query]

> Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32000,"message":"transaction underpriced"\}}}"

Increase the gas limit for the transaction in your wallet. Check your wallet's documentation to learn how to increase gas limit.

> Swap failed: Error: \[ethjs-query] while formatting outputs from RPC '{"value":{"code":-32603,"data":{"code":-32603,"message":"handle request error"\}}}'

Cause unclear. Try these steps before trying again:

1. Increase gas limit
2. Increase slippage
3. Clear cache

## **Issues with Profile**

### Oops! We couldn't find any Zexdex NFT Profiles in your wallet.

We're looking into the reasoning behind this problem. In the meanwhile, please try the workaround.

{% tabs %}
{% tab title="Workaround 1" %}

1. Go to "NFT Marketplaces" page, then come back to profile page.\
   If you can’t find the link, go to [https://zexdex.app/nftmarketplaces/](https://zexdex.app/nftmarketplaces/) directly.
2. Retry profile creation.

{% endtab %}

{% tab title="Workaround 2" %}
Change the environment.

- Clear the cache and retry.
- Retry on different browser.
- Retry on different wallet apps.
- Retry on the different network (switch between Wi-Fi and cellular)

{% endtab %}
{% endtabs %}

### Checking username keeps spinning

There are two possible causes.

1. You have multiple wallets installed on the browser.
2. Network issue.

{% tabs %}
{% tab title="Solution 1" %}
Root cause: You have multiple wallets installed on the browser.\

It may make a conflict between wallets. This is out of ZexdexApp's control and we can do nothing.

1. Have only single wallet installed on browser, remove the others.
2. Reconnect the wallet and retry setting username again.

{% endtab %}

{% tab title="Solution 2" %}
Root cause: Network is unstable.

You have to retry.

1. Delete whatever has been entered in the text field completely.
2. Re-type username, then please wait for seconds.
3. If it doesn’t work, reload the page and retry again.

{% endtab %}
{% endtabs %}
