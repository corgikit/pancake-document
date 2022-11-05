# zDEX Tokenomics

![](../../.gitbook/images/220811-en.png)

## **Emission rate** <a href="#emission-rate" id="emission-rate"></a>

### **Per block**

| **Metric**             | **Emission/block (zDEX)** | **Emission/day (zDEX)** |
| ---------------------- | ------------------------: | ----------------------: |
| Emission               |                        40 |               1,152,000 |
| Burned Weekly          |                   \~28.84 |               \~830,800 |
| **Effective Emission** |             **\~11.16\*** |         **\~321,200\*** |

{% hint style="info" %}
On August 11, 2022, Chefs implemented some configuration upgrades to take full advantage of MasterChef v2. It eliminates the 45,000 zDEX daily burn for the legacy lottery injections. Those burns will now be handled by MasterChef v2 directly along with the usual weekly zDEX burn. Therefore, the effective emissions are now even lower.
{% endhint %}

In addition to the above, a dynamic amount of zDEX is also [minted to the Dev address](https://bscscan.com/address/0xceba60280fb0ecd9a5a26a1552b90944770a4a0e#tokentxns) at a rate of 9.09%. This means that if 100 zDEX are harvested, then 9.09 zDEX is minted in addition and sent to the Dev Address.

{% hint style="warning" %}
All zDEX minted to the Dev address is burned in the weekly burn and never enters circulation.&#x20;

As such, we haven't included it in the above emission rate.
{% endhint %}

## Distribution <a href="#distribution" id="distribution"></a>

| Distributed to                | Reward/block (% of emission) | Reward/block (total zDEX) |           Reward/day |
| ----------------------------- | ---------------------------: | ------------------------: | -------------------: |
| Farms                         |                      \~5.03% |                  \~2.0138 |      58,000 (approx) |
| Lottery                       |                      \~0.35% |                  \~0.1389 |       4,000 (approx) |
| zDEX Staking Pool             |                      \~22.5% |                       \~9 |     259,200 (approx) |
| **Total Daily zDEX Emission** |                              |                           | **321,200 (approx)** |

## **Other Deflationary Mechanics** <a href="#other-deflationary-mechanics" id="other-deflationary-mechanics"></a>

{% hint style="info" %}
The burning process is currently manual. [View burn transactions here](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82?a=0x000000000000000000000000000000000000dead).
{% endhint %}

As well as the above, zDEX is also burned in the following ways:

- **0.0575%** of every trade made on ZexdexApp V2
- **100%** of zDEX sent to the Dev address
- **100%** of zDEX performance fees from IFOs
- **100%** of zDEX spent on Profile Creation and NFT minting
- **100%** of zDEX bid during Farm Auctions
- **20%** of zDEX spent on lottery tickets
- **20%** of all profits from Perpetual Trading
- **45,000** zDEX per day (historically assigned to the lottery)
- **3%** of every BNB Prediction markets round is used to buy zDEX for burning
- **3%** of every zDEX Prediction markets round
- **2%** of every yield harvest from all the flexible staking positions in zDEX pool
- **2%** of every NFT sale on the NFT Market is used to buy zDEX for burning

## Why is the zDEX burn manual?

To hit the ground running, ZexdexApp launched as an MVP (minimum viable product) with the MasterChef contract emitting 40 zDEX per block. For that reason, the early team didn't add additional functions such as the ability to customize the zDEX minting logic. The team has been controlling zDEX emissions through a manual burn process by creating two pools in MasterChef v1:

- Legacy Lottery Pool (PID - 137) - burned zDEX from the lottery
- Burn Pool (PID - 138) - burned zDEX per block

These pools work similarly to the farms, where the Chefs can adjust the percentage of the 40 zDEX per block allocated to it after each zDEX emission reduction vote.

**However, in April 2022, ZexdexApp migrated to a new MasterChef v2 contract.** The ratio of the zDEX burn per block is finally controlled by a dedicated contract. This allows the burn to be much more accurate.

{% hint style="warning" %}
Due to MasterChef v2 occasionally harvesting the full 40 zDEX per block. The supply shown on the homepage (or some 3rd party trackers) might suddenly jump by several million zDEX.

Don't worry - **EMISSION IS NOW CONTROLLED CAREFULLY BY MASTERCHEF V2. zDEX TO BURN WILL NEVER ACTUALLY ENTERS CIRCULATION!**
{% endhint %}

## How to Confirm zDEX Supply for yourself

To confirm that the circulating zDEX supply shown on the ZexdexApp homepage is correct,&#x20;

1. Head to the zDEX token contract on BscScan and [see how much zDEX is held by the Burn Address.](https://bscscan.com/token/0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82#balances) That's the total amount of zDEX that's been burned (removed from circulation FOREVER, and impossible to ever retrieve).
2. Then, subtract this burned amount from the "Total Supply" that BscScan shows.
3. This gives you the actual zDEX supply.

#### **Read more about zDEX's deflationary mechanics on the next page.** <a href="#read-more-about-zDEXs-deflationary-mechanics-on-the-next-page" id="read-more-about-zDEXs-deflationary-mechanics-on-the-next-page"></a>
