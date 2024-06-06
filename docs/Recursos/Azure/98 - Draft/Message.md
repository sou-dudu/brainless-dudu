In the terminology of [[distributed applications]], **messages** have the following characteristics:

- A message contains raw data, produced by one component and consumed by another component.
- A message contains the data itself, not just a reference to that data.
- The sending component expects the destination component to process the message content in a certain way. The overall system integrity might depend on both sender and receiver doing a specific job.