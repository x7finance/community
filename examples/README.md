# Token Pair / Loan Example - [mainnet]

Token: `X7-TESTTOKEN-01`\
Example:
Contract: https://etherscan.io/token/0x7001c80e6AB7F35d2Bcc153F73EB03b88471c151 \
Liquidity Loan: `(X7ILL001)`\
Loan Duration: `24 Hours`\
Loan Details:

```
Name:
Simple Loan

Loan Origination Fee:
25% of borrowed capital (4x leverage)

Loan Retention Premium:
0%

Principal Repayment Condition:
100% due by end of loan term

Liquidation Conditions:
Failure to pay the principal by the end of the loan will result in liquidation
```

<br/>
<br/>

Token: `X7-TESTTOKEN-02`\
Contract: https://etherscan.io/token/0x2ed6cc5a10bfa1045f6a6d05e16fdedb80113a96 \
Liquidity Loan: `(X7ILL002)`\
Loan Duration: `24 Hours`\

Loan ID 2 and Loan ID 3 are still in repayment and we will see them fully paid to demonstrate the successful origination and repayment of each of the current loan terms.

Loan Details:

```
Name: Amortizing Loan with interest

Loan Origination Fee:
10% of borrowed capital (10x leverage)

Loan Retention Premium:
6.25% in premiums due by the end of each quarter of the loan term

Principal Repayment Condition:
25% of borrowed capital due by the end of each quarter of the loan term

Liquidation Conditions:
Failure to pay the principal or premium on time will result in full liquidation up to the liability amount
```

<br/>
<br/>

Token: `X7-TESTTOKEN-03`\
Contract: https://etherscan.io/token/0xe1f759353cb857693b59eec44877dedf98c970c4 \
Liquidity Loan: `(X7ILL003)`\
Loan Duration: `24 Hours`\
Loan Details:

```
Name:
Interest Only Loan

Loan Origination Fee:
15% of borrowed capital (6.66x leverage)

Loan Retention Premium:
6.25% in premiums due by the end of each quarter of the loan term

Principal Repayment Condition:
100% of borrowed capital due by the end of the loan term

Liquidation Conditions:
Failure to pay the principal or premium on time will result in full liquidation up to the liability amount
```

<br/>
<br/>

Token: `X7-TESTTOKEN-04`\
Contract: https://etherscan.io/token/0x4be45ec99beb6fc43053addd061a36e082a05e21 \
Liquidity Loan: `(X7ILL003)`\
Loan Duration: `24 Hours`\
Mint: NFT#4
https://etherscan.io/token/0x74001c747b6cc9091ee63bc9424dff633fbac617?a=4 \
Loan Details:

```
Name:
Interest Only Loan

Loan Origination Fee:
15% of borrowed capital (6.66x leverage)

Loan Retention Premium:
6.25% in premiums due by the end of each quarter of the loan term

Principal Repayment Condition:
100% of borrowed capital due by the end of the loan term

Liquidation Conditions:
Failure to pay the principal or premium on time will result in full liquidation up to the liability amount
```

<br/>
<br/>

Token: `X7-TESTTOKEN-05`\
Example: Loan ID 5 will be used to demonstrate liquidation with high gas on transfer and balance checks as well as transfer locks (all honeypotting techniques).
Contract: https://etherscan.io/token/0x346555606112ac5e95db17994ed073e76b697b32 \
Liquidity Loan: `(X7ILL001)`\
Loan Duration: `24 Hours`\
Loan Details:

```
Name:
Simple Loan

Loan Origination Fee:
25% of borrowed capital (4x leverage)

Loan Retention Premium:
0%

Principal Repayment Condition:
100% due by end of loan term

Liquidation Conditions:
Failure to pay the principal by the end of the loan will result in liquidation
```

<br/>
<br/>

Token: `X7-TESTTOKEN-06`\
Example: Attempt access loaned liquidity - via nefariously minting additional tokens outside of cirulation.\
Contract: https://etherscan.io/token/0xfABcFAd1d98cA3DEBa4eb2d431e0400EE90Cc45c \
Liquidity Loan: `(X7ILL001)`\
Loan Duration: `24 Hours`\
Loan Details:

```
Name:
Simple Loan

Loan Origination Fee:
25% of borrowed capital (4x leverage)

Loan Retention Premium:
0%

Principal Repayment Condition:
100% due by end of loan term

Liquidation Conditions:
Failure to pay the principal by the end of the loan will result in liquidation
```
