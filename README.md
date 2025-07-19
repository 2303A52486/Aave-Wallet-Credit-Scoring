### Aave Wallet Credit Scoring



#### Problem Statement



Decentralized finance (DeFi) does not have a conventional credit bureau. In order to encourage good borrowing and lending practices, we developed a credit score system for wallets that are interacting with Aave V2 on Polygon.



#### Approach



My system assigns every wallet a **credit score between 0 and 1000** depending on the user's transaction history. The greater the score, the more secure and responsible user.



#### Main Features Utilized



* **Deposits**: Total assets deposited.
* **Borrows**: Customer's outstanding balance borrowed.
* **Repayments**: Repayment of loans.
* **Liquidations:** Frequency of how many times the wallet was liquidated.
* **Leverage Ratio**: Borrowed money compared to deposits.
* **Repayment Ratio**: Repayment to borrowed amount.
* **Behavioral Sequences**: Transaction action patterns (extracted as n-grams).



#### Scoring Logic



Derived artificial scores from behavioral heuristics that reflect wallet behavior:



* Reward wallets that repay loans and are low-leverage.
* Sanction wallets that are repeatedly liquidated.
* Encourage healthy deposit-borrow-repay cycles.



#### Workflow

1. Unpack raw wallet transaction JSON.
2. Pull out action sequences and transaction-level characteristics.
3. Construct health-based pseudo-scores.
4. Train a regression model to predict scores.
5. Display final scores and create a distribution graph.
