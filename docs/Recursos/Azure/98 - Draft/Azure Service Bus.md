[Service Bus](https://azure.microsoft.com/services/service-bus/) is a message-broker system intended for enterprise applications. These apps often utilize multiple communication protocols, have different data contracts and higher security requirements, and can include both cloud and on-premises services. Service Bus is built on top of a dedicated messaging infrastructure designed for exactly these scenarios.

Scenario of use for service bus queus:
- Need an At-Most-Once delivery guarantee.
- Need a FIFO guarantee.
- Need to group messages into transactions.
- Want to receive messages without polling the queue.
- Need to provide a role-based access model to the queues.
- Need to handle messages larger than 64 KB but less than 100 MB. The maximum message size supported by the standard tier is 256 KB and the premium tier is 100 MB.
- Queue size won't grow larger than 1 TB. The maximum queue size for the standard tier is 80 GB and for the premium tier, it's 1 TB.
- Want to publish and consume batches of messages.

Scenario of use for service bus topics:
- Need all the features provided by Service Bus queues, and in addition implement a pub-sub pattern where messages can be routed to one of multiple subscriptions, each with its own independent receivers

Temas
Un _tema_ de Service Bus es similar a una cola, pero puede tener varias suscripciones.
![[Pasted image 20240516183717.png]]

Cola
Una _cola_ de Service Bus es una ubicación de almacenamiento temporal simple para los mensajes. Un componente de envío agrega un mensaje a la cola.
![[Pasted image 20240516183711.png]]


[[Creación de una cola de Service Bus]]
