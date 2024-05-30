---
description: Voting, solutions and rewards!
---

# 👐 Governance

**Standards and Solutions**

In the DeFi space, every protocol needs to possess a specific amount of liquidity to ensure smooth operations. Efficient management of liquidity and appropriate distribution of rewards are critical factors that determine the success of DeFi protocols.

We align protocol emissions with fees generated, not simply liquidity. To do this, it would allow protocols and other large stakeholders to become veNFT "voters," using their locked voting power to direct future emissions and collect fees from the pools they voted for.

At Skylar, we allow voters to make only one "active" voting decision (i.e., Voter.vote(), Voter.reset()) every epoch (note: this does not include the Voter.poke() function). Voters who exploit the system can direct emissions towards unproductive gauges, particularly those for pools they own entirely. In response, Skylar has implemented two measures to ensure that the system is fair, transparent, and economically aligned.

Firstly, we have integrated an on-chain governor to whitelist pairs used in gauges. Proposals can be submitted only by voters who hold a minimum of 0.02%, and a quorum of 4% is necessary to approve proposals. We have eliminated the ability to whitelist gauges with a fee to guarantee that those who do so are economically aligned with our system.

Secondly, to incentivize voters to direct emissions towards productive liquidity, we have increased the protocol fee from 0.01% to 0.02%. These changes intend to strengthen our system's integrity and guarantee that our voters are aligned with our objectives.

A lending protocol is an essential component of DeFi composability. It's a decentralized platform where users, bots, and other DeFi protocols can access a public marketplace of assets. Skylar offers a comprehensive set of lending features, with a particular focus on the assets handled on Base.

***

#### Gauge Voting

The allocation of emitted assets to specific markets in each epoch is determined by $veSKLR token holders through a voting process on their preferred market gauges. The proportion of $veSKLR emissions distributed to a liquidity gauge is directly proportional to the total votes it receives. As an incentive, voters receive 100% of the protocol fees and bribes collected through the market for which they voted.

$veSKLR NFT-related activities, including gauge voting, may be conducted at any time during an epoch. As a result, Voter.reset() (which is used to reset an NFT vote state before merging it into another $veSKLR NFT) and Voter.poke() (which is used to recast votes for the current epoch to direct emissions) are considered actions for the current epoch.

Notably, unused $veSKLR voting power is still considered in the vote calculation, as the weight of the vote is calculated based on the locked vesting slope upon epoch flip. Therefore, it is advisable to cast the entire 100% of voting power to avoid any unexpected results.
