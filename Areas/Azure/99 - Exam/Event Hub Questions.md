Applications that publish messages to Azure Event Hubs frequently get the best performance using Advanced Message Queuing Protocol (AMQP) because it establishes a persistent socket.

True: Publishers can use either HTTPS or AMQP. AMQP opens a socket and can send multiple messages over that socket

By default, how many partitions does a new event hub have?

Event Hubs default to four partitions. Partitions are the buckets within an event hub. Each publication goes into only one partition. Each consumer group might read from one or more than one partition.

 
What is the maximum size for a single publication (individual or batch) allowed by Azure Event Hubs?
The maximum size for a single publication (individual or batch) allowed by Azure Event Hubs is 1 MB.