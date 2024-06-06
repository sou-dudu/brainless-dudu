A transaction is a logical group of database operations that run together.
Transactions are often defined by a set of four requirements call _ACID guarantees_. ACID is an acronym for _atomicity_, _consistency_, _isolation_, and _durability_.

- _Atomicity_ means a transaction must run exactly once, and it must be atomic. Either all of the work is done or none of it is. Operations within a transaction usually share a common intent and are interdependent.
- _Consistency_ ensures that the data is consistent both before and after the transaction.
- _Isolation_ ensures that each transaction is unaffected by other transactions.
- _Durability_ means that changes made as a result of a transaction are permanently saved in the system. The system saves data that's committed so that even in the event of a failure and system restart, the data is available in its correct state.
Type of transaction:
- Online transaction processing (OLTP): TP systems commonly support many users, have quick response times, and handle large volumes of data.
- _Online analytical processing (OLAP)_ systems commonly support fewer users, have longer response times, can be less available, and typically handle large transactions or complex transactions.

[Transactions: Evaluate your data types]([https://learn.microsoft.com/en-us/training/modules/choose-storage-approach-in-azure/4-transactions))
[[Transaction questions]]
