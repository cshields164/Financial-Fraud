# Financial Fraud Project

We received a dataset that of bank transactions to see which strategies we can take in order to successfully capture as many fraudulent transactions as possible, while also minimizing false positives. The data sttributes given within the dataset were step which is the unit of time that represents hours in the dataset, type of transaction occured, amount of money transferred, name of the original account, original account balance before the transaction, original account balance after the transaction, name of the destination account, destination account balance before the transaction, destination account balance after the transaction, isFlaggedFraud naive model that flags a transaction as fraudulent if it is greater than 200,000, and isFraud is the target to determine if a malicious transaction occured that aimed to transfer funds out of a victims bank account before the account owner could secure their information.

# Observations

I was focused on what columns needed to be removed that did not add any value to detecting fraudulent transactions. After evaluating the isFraud and isFlaggedFraud columns, I noticed that isFlaggedFraud only determined 16 transactions to be fraudulent as opposed to isFraud that flagged 8,213 transactions to be fradulent. This happened because the isFlaggedFraud column only recognized the transactions that had the amount of 200,000 or more as fraudulent. So I removed this column from the dataset.

I also removed the step column from the dataset because it gave no siginificant value or information for the analysis.

After close analysis of the rest of the dataset, the data is heavily right skewed. The average amount of transactions that occured across the dataset is 1.798619e+05. The only two transactions that fraud occured was transfer and cash out transactions. There were 4,116 fraudulent cash out transactions and 4,097 fraudulent transactions.

The insights I gathered from my EDA is that the distribution for most of the columns is heavily right skewed. The top 3 transaction types to occur is cash out, payment, and cash in.

After running the test random forest classifier, I received an accuracy score of 99%, which seems very strange because the isFraud column didn't have that high of an accuracy score. Only 8,213 were recognized as fraud out of 6362620.