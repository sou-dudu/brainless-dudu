Use: implement complex stateful functions in a serverless-environment
Case of use:  your company currently follows a manual approval process for project-design proposals
Beneficts: 
- They enable you to write event driven code. A durable function can wait asynchronously for one or more external events, then perform a series of tasks in response to these events.
- You can chain functions together. You can implement common patterns such as fan-out/fan-in, which uses one function to invoke others in parallel, then accumulate the results.
- You can orchestrate and coordinate functions and specify the order in which functions should execute.
- The state is managed for you. You don't have to write your own code to save state information for a long-running function.
Orchestation function: 
- You can define the workflows in code
- Functions can be called both synchronously and asynchronously
- Azure checkpoints the progress of a function automatically when the function awaits
[[Orchestation functions types]]
[[Durable functions patterns]]
[[Comparison Durable functions with Logic Apps]]
