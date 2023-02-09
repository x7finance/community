## Xchange: A Leveraged Initial Liquidity Decentralized Exchange

X7’s Decentralized Exchange is a peer-to-peer Automated Market Making (AMM) platform integrated with a novel trustless, permissionless on-chain undercollateralized loan origination and servicing system known as the Lending Pool. This section will describe the core functionality of the operations of DEX.

### Technical Abstract

Xchange is built on a forked version of the Uniswap V2 Factory, Liquidity Pair, and Router contracts. There are two notable changes:

- The Liquidity Pair contract has added safeguards to allow it to support leveraged liquidity additions that ensure the leverage remains collateralized and can be liquidated in the event of loan default and appropriately manage Liquidity Tokens during an active Initial Liquidity Loan.
- The liquidity provider fee has been reduced from 0.3% to 0.2%. This reflects the reality that in many cases the liquidity providers for tokens are actually the token creators and the benefit they receive is more often via token price appreciation or token fees, not liquidity provision.

Additionally, the User Interface will allow a seamless experience trading across other Uniswap V2 style decentralized exchange pairs (such as Uniswap or SushiSwap).
