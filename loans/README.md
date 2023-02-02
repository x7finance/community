# X7 Finance Loan Terms

The lending process delegates the loan terms to standalone smart contracts (see whitepaper below for more details). These loan terms contracts must be deployed, and then “added” or “removed” from the Lending Pool as “available” loan terms for new loans. The DAO will be able to add or remove these term contracts.

Loan term contracts may be created by any interested third party, enabling a market process by which new loan terms may be invented, provided they implement the proper interface.

The reference implementations that will be active at launch will have the following terms:

🌟 **X7 Initial Liquidity Loan Term (001) - X7ILL001**\
---> Min Loan: 0.5 ETH\
---> Max Loan: 5 ETH\
---> Leverage: (4x leverage)\
---> Number of repayment periods: 1\
---> Number of premium periods: 0\
---> Min Loan Duration: 1\
---> Min Loan Duration: 7

<br>

🌟 **X7 Initial Liquidity Loan Term (002) - X7ILL002**\
---> Min Loan: 0.5 ETH\
---> Max Loan: 5 ETH\
---> Leverage: (10x leverage)\
---> Number of repayment periods: 4\
---> Number of premium periods: 4\
---> Loan Retention Premium: 6.25% in premiums due by the end of each quarter of the loan term\
---> Min Loan Duration: 1\
---> Min Loan Duration: 7

<br>

🌟 **X7 Initial Liquidity Loan Term (003) - X7ILL003**\
---> Min: 0.5 ETH\
---> Max: 5 ETH\
---> Leverage: (6.66x leverage)\
---> Number of repayment periods: 1\
---> Number of premium periods: 4\
---> Loan Retention Premium: 6.25% in premiums due by the end of each quarter of the loan term\
---> Min Loan Duration: 1\
---> Min Loan Duration: 7
