## Lending Functionality

Lending is a fully automatic process managed fully by Xchange’s interfacing with the Lending Pool via Initial Liquidity Loans.

For end-users, wanting to participate in lending: a user selects the amount of Ether to deposit or withdraw from the Lending Pool. Receipts for deposit are issued in X7 deposit, redeemable 1-to-1 with Eth, and may be staked for a portion of the loan fees.

### Initial Liquidity Loan

An initial liquidity loan provides a mechanism to add initial liquidity to an automated market making trading pair with borrowed capital. The terms and conditions for borrowing this capital and returning it to the lender provide for the lender and the borrower to manage their cost of capital and repayment schedules in a way that supports the nature of the offering and the size and duration of the loan.

### Initial Liquidity Loan Terms

Loan terms are defined by standalone smart contracts that provide the following:

1. Loan origination fee
1. Loan retention premium fee schedule
1. Principal repayment condition/maximum loan duration
1. Liquidation conditions and Reward
1. Loan duration

### Loan Duration

Due to capital management considerations and to be agile in dialing in product-market fit, initial loan durations will be limited to 10 to 90 Days.

These initial durations reflect the expected initial product market of DeFi token launches. As the market expands to longer and more well-defined projects, the durations are expected to be longer and the origination and premium fee structures may become more competitive with other forms of financing.

### Loan Liquidation

Anyone may liquidate eligible loans through a transaction. Doing so will result in the borrowed capital being returned to the lender (Lending Pool or third-party lender) and the liquidator will receive the liquidation bounty.

### Initial Liquidity Loan Origination

Initial Liquidity Loans can be funded in two ways, Lending Pool originated loans and Tokenized loans that may be fulfilled by any wallet.

### Lending Pool Origination

If the Lending Pool has sufficient liquidity to fund a loan, the loan will immediately be funded and the AMM liquidity pair will be created. Loan origination fees will be collected and proceeds will be distributed throughout the X7 ecosystem. A portion of the origination fee will feed back into the Lending Pool to grow the capital available for automatic lending.

### Tokenized Loans

When a leveraged pair loan is requested that cannot be serviced due to insufficient liquidity within the Lending Pool, the request will cause an NFT to be minted. This NFT can be claimed by funding the loan, and results in an instantaneous return to the claimer of part of the loan origination fee. Possession of the NFT grants the holder a portion of the premium returns in the future as well as rights to claim the initial lent principal.

This mechanism will allow for a more effective bootstrapping period during which the Lending Pool may not have the proper liquidity to meet loan demand.

It will also provide a means for the lending platform to meet truly extraordinary lending requirements where third party liquidity providers can provide massive initial liquidity for an immediate return.

Since these loans will be represented by ownership of an NFT and the benefits accrue to the owner of the NFT, the NFT itself may be transferred, auctioned, bought, sold, or held by smart contract to create a variety of ways that a lender may attempt to maximize their profit, limit their short term exposure, or otherwise draw upon their lent capital before the loan term concludes.

DeFi participants are encouraged to create private “Lending Pools” that will attempt to fund loans (a riskless activity) and pay returns to liquidity providers. The X7 ecosystem will not provide this particular capability.

### Lending Terms Governance

The lending process delegates the loan terms to standalone smart contracts (see above and below for more details). These loan terms contracts must be deployed, and then “added” or “removed” from the Lending Pool as “available” loan terms for new loans. The DAO will be able to add or remove these term contracts.

Loan term contracts may be created by any interested third party, enabling a market process by which new loan terms may be invented, provided they implement the proper interface.

The reference implementations that will be active at launch will have the following terms:

### Simple Loan

| Loan Name                           | Simple Loan                                                                                                    |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Loan Origination Fee                | 25% of borrowed capital, payable within the transaction for adding initial liquidity                           |
| Loan Retention Premium Fee Schedule | No interest payment                                                                                            |
| Principal Repayment Condition       | 100% principal must be returned by the end of the loan term.                                                   |
| Liquidation conditions              | Failure of full repayment of principal by the end of the loan term will make the loan eligible for liquidation |
| Liquidator reward                   | 5% of the loan origination fee will be reserved for a liquidation bounty.                                      |

### Amortizing Loan with interest

| Loan Name                           | Amortizing Loan with interest                                                                                                                                |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Loan Origination Fee                | 10% of borrowed capital, payable within the transaction for adding initial liquidity                                                                         |
| Loan Retention Premium Fee Schedule | 6.25% of borrowed capital payable by the end of each quarter of the loan term for a total retention premium fee of 25% of borrowed capital                   |
| Principal Repayment Condition       | 25% of the capital must be repaid on each quarter                                                                                                            |
| Liquidation conditions              | Failure to pay a premium + principal payment by its due date or repay the principal by the end of the loan term will make the loan eligible for liquidation. |
| Liquidator reward                   | 5% of the loan origination fee will be reserved for a liquidation bounty.                                                                                    |

### Interest Only Loan

| Loan Name                           | Interest Only Loan                                                                                                                               |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Loan Origination Fee                | 15% of borrowed capital, payable within the transaction for adding initial liquidity                                                             |
| Loan Retention Premium Fee Schedule | 6.25% of borrowed capital payable by the end of each quarter of the loan term for a total retention premium fee of 25% of borrowed capital       |
| Principal Repayment Condition       | 100% principal must be returned by the end of                                                                                                    |
| Liquidation conditions              | Failure to pay a premium payment by its due date or repay the principal by the end of the loan term will make the loan eligible for liquidation. |
| Liquidator reward                   | 10% of the loan origination fee will be reserved for a liquidation bounty                                                                        |
