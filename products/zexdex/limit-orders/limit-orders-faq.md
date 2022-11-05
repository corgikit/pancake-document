# Limit Orders Frequently Asked Questions

{% hint style="info" %}
Use the sidebar to find answers to your questions quickly!
{% endhint %}

## General Concerns

### Why was my order not carried out?

Limit orders are executed when the price specified on the interface is met; however, due to gas fluctuations, the actual execution price may differ from the price specified on the interface. The execution price and the desired price should usually be nearly identical; however, if you submitted a particularly small order (1000$), the execution price may be slightly higher to account for fees.

As a result, your order may not be carried out because:

- Due to price impact, it was not possible to fill the entire order at the desired price and amount. One of the tokens in the limit order has a transaction fee (see below).

**Please consult the UI denoting the real execution price before submitting an order.**

{% hint style="info" %}
Please keep in mind that the order history table receives data from Subgraph and may display slightly delayed information.
{% endhint %}

### Is it possible to place a limit order for tokens with a fee on transfer?

**No.** Transfer fee tokens should not be used with limit orders. Proceed entirely at your own risk.

### How do I configure slippage when using limit orders?

Limit orders do not allow for slippage. Limit orders guarantee that you will receive no less than the specified output amount (20 BNB) for your input amount (1000 zDEX) if the price of the pair reaches the desired price. **Please keep in mind that tokens with a fee on transfer should not be used with limit orders** (read above)

### The true execution price indicates that the order "never executes." What precisely is this?

It basically means you're trying to swap a very small number of tokens, and there aren't enough tokens to cover the gas fee. Increase the size of the "input" field in general to fix this error.

### Do my limit orders have an expiration date?

Orders that are open will remain open indefinitely until they are executed or cancelled by users. In the near future, a customizable expiration date feature is planned.

### Why am I unable to place limit orders below the market price?

To sell below the market price, you must use **Stop Limit Orders** rather than limit orders. The Stop Limit Orders feature will be available soon.

### I placed an order, but it isn't showing up in the order table or is stuck at "pending."

Because the order history is derived from the subgraph, it may contain slightly delayed information. Delays are usually no more than a couple of minutes at most. Please see the subgraph indicator in the order history table's bottom right corner.
