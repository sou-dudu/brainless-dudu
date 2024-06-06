Events are more likely to be used for broadcasts, and are often ephemeral.

Messages are more likely to be used where the distributed application requires a guarantee that the communication will be processed.

Question to be considered:
* Does the sending component expect the communication to be processed in a particular way by the destination component?
	* yes: message
	* no: event