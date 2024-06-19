- **Client** functions are the entry point for creating an instance of a Durable Functions orchestration. They can run in response to an event from many sources, such as a new. HTTP request arriving, a message being posted to a message queue, an event arriving in an event stream. You can write them in any of the supported languages.
- **Orchestrator** functions describe how actions are executed and the order in which they're run. You write the orchestration logic in code (C# or JavaScript)
- **Activity** functions are the basic units of work in a Durable Functions orchestration. An activity function contains the actual work performed by the tasks being orchestrated.