---
description: Fixed-Term zDEX Staking and IFO Allocations
---

# izDEX

### **What is izDEX?**

izDEX is similar to “IFO credits” from the previous IFO zDEX staking pool, which was retired during the MasterChef v2 migration. After this update, izDEX will determine the maximum zDEX commit limit in the ZexdexApp IFO public sales. For example, if you have 200 izDEX, you will be able to commit 200 zDEX in any upcoming IFO public sales.

**izDEX is NOT a new token, it is a numerical metric being used by the ZexdexApp IFO system.**

### How is izDEX calculated?

The number of izDEX you have is based on the number of zDEX staked in the fixed-term zDEX staking pool and the total staking duration of your current fixed-term staking position.

izDEX works based on a staking duration threshold for all izDEX users.

If your staking duration is above the threshold, the number of izDEX you have is equal to the number of the zDEX in your staking position.

If your staking duration is below the threshold, the number of izDEX you have will be linear decreased and adjusted.

If your staking position is ended, the number of izDEX you have is 0.

For example, if the threshold is 20 weeks:&#x20;

- Your current fixed-term staking position has a duration of 25 weeks and 200 staked zDEX. Then the number of izDEX you have is 200.&#x20;
- Your current fixed-term staking position has a duration of 10 weeks and 200 staked zDEX. Then the number of izDEX you have equals 200 × (10 ÷ 20) = 100.&#x20;
- Your current fixed-term staking position has a duration of 2 weeks and 200 staked zDEX. Then the number of izDEX you have equals 200 × (2 ÷ 20) = 20.&#x20;
- Your current fixed-term staking position has a duration of 2 weeks and 200 staked zDEX. But the position is ended. Then the number of izDEX you have is 0.

|                  | Your staking duration is equal to or longer than the threshold | Your staking duration is shorter than the threshold                  |
| ---------------- | -------------------------------------------------------------- | -------------------------------------------------------------------- |
| **izDEX Amount** | Equals your Locked zDEX Amount                                 | Equals your Locked zDEX Amount x (Your Staking Duration / Threshold) |

### How to check the number of izDEX I have?

![](../../.gitbook/images/image3.png)

You can check the number of izDEX you have in the IFO page [here](https://zexdex.app/ifo).

### **How to increase the number of izDEX I have?**

You can increase the number of izDEX you have by:

- Adding more zDEX to your fixed-term staking position in the zDEX staking pool.
- Extend your fixed-term staking durations if your current durations is shorter than the threshold.

\***\*![](../../.gitbook/images/image2.png)\*\***

You can preview the number of izDEX generated from your staking position when adjusting or initializing the fixed-staking.

### What is the threshold for izDEX calculations?

Between each IFOs, the kitchen will optimize the threshold based on the average staking duration of the fixed-term staking zDEX pool. The adjustment will be published on all social channels.

![](<../../.gitbook/images/image (134).png>)

You can check the current threshold for izDEX calculations by hovering or tapping the underlined izDEX text in the zDEX staking pool window.
