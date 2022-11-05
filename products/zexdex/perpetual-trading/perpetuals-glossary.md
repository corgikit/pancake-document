# Glossary

**Here you will find defined all the terms inherent in futures trading**

### **Perpetual Trading**

Perpetuals, also known as perpetual swaps or perps, are a type of futures contract that does not have an expiration date.

### **Leverage**

Leverage is a trading strategy. Traders can use it to increase their market exposure by paying less than the full amount of the investment. To put it simply, you borrow money to leverage your investment.

![](https://lh5.googleusercontent.com/S4CpgIaapprJpet3GI9UvkGA2Vncl6ywSA8848SLOG5M73v2ILcSunlPMOxpWg9UJmKui4Vb6BDQcUugWP1aYMAVl9_QPioIxT9sFRuY-EEtuSXgCn_D8Muwqh60PFr3EcEu3kkH)

### **Margin**

Margin is the assurance you provide for your leveraged positions. It has two modes of operation:

- Cross Margin Mode: The asset cross margin balance is shared by all cross positions under the same margin asset. Your assets' full margin balance, as well as any remaining open positions under the asset, may be forfeited in the event of liquidation.
- Isolated Margin Mode: Limit the amount of margin allocated to individual positions to manage risk. If a position's margin ratio reaches 100%, the position will be liquidated. This mode allows you to add or remove margin from positions.

![](https://lh3.googleusercontent.com/zVEa2C_uhxdfB83PnT0jPQ3lbs5hJ8IY4cOe5KgxOiypTxV0CC1mXHouC9EhR2ukRmnMIXzk71JkEwPLmXAeK0RuP0xDsqX7c6P-X-7bPdqN3Xrfzxhub2wV55_ZKRNTy8WoCpUs)

**Margin Ratio**: Margin Ratio = (Maintenance Margin)/(Margin Balance). When the Margin Ratio reaches 100%, your positions will be liquidated.

**Maintenance Ratio**: The bare minimum of margin balance required to maintain open positions.

**Margin Balance** = Wallet Balance + Unrealized PNL. Once Margin Balance <= Maintenance Margin, your positions will be liquidated.

![](https://lh6.googleusercontent.com/BGaNOmsOkew_Cf9f6zcP2bW4Die0-uZnoui7QVYY24oDFtQkgIB5Vq1dLo7XgkA3LKyisoK-5Cs0uSN7fl19aa9nvDDAzWCVdgnJ3xNGHkDchaJMQf1G0gvXmDDvR2DvAih1D7tS)

### Assets:

**Deposit**: Deposit your funds into your futures account

**Withdraw**: Withdraw your funds from your futures account to your wallet

**Balance**: Wallet Balance = Total Net Transfer + Total Realized Profit + Total Net Funding Fee - Total Commission.

**Unrealized PNL**: Unrealized profit and loss on this position calculated based on Mark Price, and return on equity percentage.

**Modes:**&#x20;

- Single Asset Mode: Allows USDS-M Futures trading by using only the symbol's single margin asset. The PNL of identical margin asset positions can be offset. Cross Margin and Isolated Margin modes are supported.
- Multi-Asset Mode: Trading USDS-M Futures across multiple margin assets. PNL can be distributed among the various margin asset positions. Only Cross Margin Mode is supported.

{% hint style="info" %}
Multi-Assets Mode cannot be activated if there are open positions or open orders in USDS-M Futures. The Multi-Assets Mode is only available for USDS-M Futures. Please read the guide thoroughly before activating Multi-Assets Mode to better manage USDS-M Futures account risk when using Multi-Assets Mode.
{% endhint %}

![](https://lh3.googleusercontent.com/iupB9UR3QMDCEO5RwjfMpqKZaQtoT53G0Sa_cYH9Neui8ttgqeFybtqOSIncZD74-4p3O-sQd6Lis2QKxGBsdgDmgutRaTUw1qKpjT-UXbpdKo-_3KzjAl3f8VSGyoLrtudoUqBr)

### Orders

**Buy/Long:** Create a Long order. In this order, you buy an asset and then sell it when the price rises. The terms "buy" and "long" are interchangeable.

**Sell/Short:** Create a Short order. In this order, you borrow an asset, sell it, and hope to repurchase it when the price falls. The terms "sell" and "short" are interchangeable.

**Limit Order:** A limit order is a purchase or sale order at a specific price or better. Limit orders are not guaranteed to be fulfilled.

**Market Order:** A market order is an order to buy or sell at the best current available price. It is executed against previously placed limit orders on the order book. As a market taker, you will pay fees when placing a market order.

**Stop Limit Order:** To understand a stop-limit order, divide it into two parts: stop price and limit price. The stop price is simply the price that causes the limit order to be triggered, and the limit price is the price of the triggered limit order. This means that once your stop price is met, your limit order will be placed on the order book immediately.

**Stop Market Order:** A stop market order, like a stop-limit order, uses a stop price as a trigger. When the stop price is reached, however, a market order is triggered instead.

**Trailing Stop:** A trailing stop is a type of order that is used to lock in profits or limit losses as a trade moves in a favorable direction. Trailing stops only move if the price moves in the right direction. It does not reverse direction once it has moved to lock in a profit or reduce a loss.

**Post Only:** Traders can only place an Order in Post-only Mode if it will be posted to the Order Book as a Maker Order. An Order submitted as a Taker Order will be rejected. Market orders may not be placed, and orders will not be filled. In post-only mode, resting orders can be canceled.

![](https://lh6.googleusercontent.com/uV8UuuqGxCwGmu9jxuL2Gf_Nt8QwkYoYCfJinEfINffyr6QjV03tZVXA46GnIxY-XKSxcrAPtrtD8JZYBHSc4ILmLd8Rm6LqHmVdSAgMK8m-4WOdt3FsnPO2MD32EG9j3ym_aSz_)

**Reduce Only:** The Reduce-Only order will only lower your position, not raise it.

![](https://lh3.googleusercontent.com/HlbLU90VSn76W1xHVgSBoke83uQpAPFzl2JBME_Dn2mElSDAYSbA51GRx2cOaAqxBe6wH02MbJxmwjrLuLoSx7Ei4AwzrnmqFjy4VEG5aUrYas7oFKVQ0CGNuiIAXjD1CdPaQurO)

**TIF instructions** allow you to specify how long your orders will remain active before being executed or expired You can use one of the following TIF instructions:

![](https://lh6.googleusercontent.com/-QaqTJU0jCsjznhULix7i2ThVM7_u7IP5a0i42TYhImt8xPLODjYCjLL5JNbRXrIDsgJRxIIGoYD8Tlq5gSdCjkAyMDat53r5WNTepB93_7bq7gDmyg1-jyblSQ8eANv_fH9bvJ-)

- **GTC** (Good Till Cancel): The order will remain active until it is either filled or canceled.
- **IOC** (Immediate Or Cancel): The order will execute immediately (either fully or partially). If it is only partially executed, the unfilled portion of the order will be canceled.
- **FOK** (Fill Or Kill): The order must be fully filled immediately. If not, it won’t be executed at all.
