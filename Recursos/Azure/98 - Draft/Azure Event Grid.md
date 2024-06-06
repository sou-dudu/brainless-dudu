Azure [Event Grid](https://azure.microsoft.com/services/event-grid/) is a fully managed event-routing service running on top of [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/). Event Grid distributes _events_ from different sources, such as [Azure Blob storage accounts](https://azure.microsoft.com/services/storage/blobs/) or [Azure Media Services](https://azure.microsoft.com/services/media-services/), to different handlers, such as [Azure Functions](https://azure.microsoft.com/services/functions/) or Webhooks. Event Grid was created to make it easier to build event-based and serverless applications on Azure.

Key concepts for azure event grid
- **[[Events]]**: What happened.
- **Event sources**: Where the event took place.
- **Topics**: The endpoint where publishers send events.
- **Event subscriptions**: The endpoint or built-in mechanism to route events, sometimes to multiple handlers. Handlers also use subscriptions to filter incoming events intelligently.
- **Event handlers**: The app or service reacting to the event.