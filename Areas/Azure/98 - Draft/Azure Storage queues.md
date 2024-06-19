[Queue storage](https://azure.microsoft.com/services/storage/queues/) is a service that uses Azure Storage to store large numbers of messages that can be securely accessed from anywhere in the world using a simple REST-based interface. Queues can contain millions of messages, limited only by the capacity of the storage account that owns it.

Benefits
- Increased reliability
- Message delivery guarantees
	- At-Least-Once Delivery
	- At-Most-Once Delivery
	- First-In-First-Out (FIFO)
- Transactional support

Scenario of use
- Need an audit trail of all messages that pass through the queue.
- Expect the queue to exceed 1 TB in size.
- Want to track progress for processing a message inside of the queue.