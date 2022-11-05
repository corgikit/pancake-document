# How to Trade

![](../../.gitbook/images/trade-guide-header.png)

## Before you go

Trading on ZexdexApp is much easier than on other exchanges. There will be no charts or jargon to confuse you, and all calculations will be done for you.

### Getting set up to trade

You will need a BNB Smart Chain-compatible wallet before you can trade. You can get one by clicking [here](../../get-started/bsc/wallet-guide.md). You will also require BEP20 tokens to trade with. You can find out how to get some by going [here](../../get-started/bsc/bep20-guide.md).

### Trading on the ZexdexApp Exchange

1. Go to the exchange page [here](https://zexdex.app/#/swap).

2. Click **Unlock Wallet** to unlock your BNB Smart Chain-compatible wallet (you can also **Connect** in the top right corner). If you haven't already connected your wallet to ZexdexApp, you can do so [here](../../get-started/bsc/connection-guide.md).

![](<../../.gitbook/images/image (12).png>)

3. In the "From" section, select the token you want to trade from the dropdown menu. BNB is the default setting.

![](<../../.gitbook/images/image (13).png>)

Whatever token you choose, make sure you have enough to trade with. The balance is displayed above the token dropdown menu.

4. In the "To" section, select the token you want to trade with. Then, by clicking inside the input box, enter an amount for your "To" currency.

![](<../../.gitbook/images/image (14).png>)

The amount in your "From" currency will be calculated automatically. If you prefer, you can type your "From" amount and have the "To" amount estimated automatically.

5. Check the details, and click the **Swap** button.

![](<../../.gitbook/images/image (15).png>)

6. A window with more details will appear. Check the details are correct.

![](<../../.gitbook/images/image (16).png>)

When you are ready, click the **Confirm Swap** button. Your wallet will ask you to confirm the action.

7. Done! You can click **View on BscScan** to see your transaction details on the explorer.

![](<../../.gitbook/images/image (17).png>)

## Why isn't my transaction going through?

ZexdexApp is a DeFi application that interacts with the wallet to complete on-chain transactions such as swapping, LP creation, staking in farms and pools, and so on.

### Gas Fees

As a result, the first step is to **ensure you have enough BNB to cover the gas fee** of on-chain transactions. Typically, the gas fee varies with the number of transactions in the queue; if there are more transactions, a higher gas fee may be required to push the transaction through. The gas fee on BNB Smart Chain typically ranges from cents to a dollar USD in BNB. Find out more about the [gas fee](https://academy.binance.com/en/glossary/gas).

### Transaction Fees

If your swapping action still fails and it displays an error for you to revise the slippage — you may want to check if the tokens you are attempting to swap have **any fees and transaction restrictions**.

It is not uncommon for tokens on BNB Smart Chain to include a **transaction fee** in their contracts; typically, these fees could be used for burning, funding a treasury of a fair launch project — for example, this [APX token has a 1% tax on every transaction](https://apollox-finance.gitbook.io/apollox-finance/apx-token/tax) for sending to a burn address, such that.

The transaction fee, whether inclusive (a portion of the swap amount is sent elsewhere than your address, resulting in a lower output than expected for the estimated input) or exclusive (requiring an additional transfer from your address to send extra tokens, resulting in a higher input than expected for the estimated output), affects the input and output amounts that you agree to when signing the transaction. Because of the tax, many transactions are unable to meet the input and output requirements.

### Swapping with Transaction Fees

Before you swap any tokens, check their website to see if they have a transaction fee mechanism (or _tax_, as many projects call it). If there is, make sure you set a slippage that is sufficient to accommodate the transaction fee — for example, if there is a 5% transaction fee, your slippage must be at least 5% plus the normal trading slippage based on your trading amount and the liquidity of the token, say 5.5%-6%.

In some extreme cases, including some scams, some tokens even have a block on most or all chain transfers, or only allow certain addresses to sell, making it impossible to successfully swap the token. Learn about the token you want to exchange and be aware of any fees or restrictions!
