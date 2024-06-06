You deploy an Azure Container Apps app and disable ingress on the container app. Users report that they are unable to access the container app. You investigate and observe that the app has scaled to 0 instances. You need to resolve the issue with the container app.

Solution applied : Enable ingress, create an HTTP scale rule, and apply the rule to the container app.

Does it work

Explanation:  
Make sure you create a scale rule or set minReplicas to 1 or more if you don’t enable ingress. If ingress is disabled and you don’t define a minReplicas or a custom scale rule, then your container app will scale to zero and have no way of starting back up.  
[https://learn.microsoft.com/en-us/azure/container-apps/scale-app?pivots=azure-cli#default-scale-rule](https://learn.microsoft.com/en-us/azure/container-apps/scale-app?pivots=azure-cli#default-scale-rule)

Default scale rule
If you don't create a scale rule, the default scale rule is applied to your container app. Make sure you create a scale rule or set `minReplicas` to 1 or more if you don't enable ingress. If ingress is disabled and you don't define a `minReplicas` or a custom scale rule, then your container app will scale to zero and have no way of starting back up.

Question 2 - App roles vs Groups

You are developing an ASP.NET Core app hosted in Azure App Service. The app requires custom claims to be returned from Microsoft Entra ID for user authorization. The claims must be removed when the app registration is removed. You need to include the custom claims in the user access token. What should you do?

Solution: Add the roles to the appRoles attribute in the app manifest.

Explanation: 
[https://learn.microsoft.com/en-us/entra/identity-platform/howto-add-app-roles-in-apps#app-roles-vs-groups](https://learn.microsoft.com/en-us/entra/identity-platform/howto-add-app-roles-in-apps#app-roles-vs-groups)

|App roles|Groups|
|---|---|
|They're specific to an application and are defined in the app registration. They move with the application.|They aren't specific to an app, but to a Microsoft Entra tenant.|
|App roles are removed when their app registration is removed.|Groups remain intact even if the app is removed.|
|Provided in the `roles` claim.|Provided in `groups` claim.|

App roles are preferred by developers when they want to describe and control the parameters of authorization in their app themselves.

Question 3 - Zero downtime deployment

You are developing a microservice to run on Azure Container Apps for a company. External HTTP ingress traffic has been enabled. The company requires that updates to the microservice must not cause downtime. You need to deploy an update to the microservices. What should you do?

Solution: Enable single revision mode.

Explanation: Zero downtime deployment using single mode.
[https://learn.microsoft.com/en-us/azure/container-apps/revisions#zero-downtime-deployment](https://learn.microsoft.com/en-us/azure/container-apps/revisions#zero-downtime-deployment)

Question 4 - Use case of BlobFuse

You have a Linux container-based console application that uploads image files from customer sites all over the world. A back-end system that runs on Azure virtual machines processes the images by using the Azure Blobs API. You are not permitted to make changes to the application. Some customer sites only have phone-based internet connections. You need to configure the console application to access the images. What should you use?

Solution: Azure BlobFuse

Explanation: Azure BlobFuse allows you to access Azure Blob Storage from Linux and Azure services as if it were a local file system, without changing the application. This is particularly useful for your scenario where you can’t modify the application and need to process images stored in Azure Blob Storage. BlobFuse provides the necessary interface between the application and Azure Blob Storage.

[https://learn.microsoft.com/en-us/azure/storage/blobs/blobfuse2-what-is](https://learn.microsoft.com/en-us/azure/storage/blobs/blobfuse2-what-is)

Question 5 - Limits  of max size per item in Azure Cosmos DB

You create an Azure Cosmos DB for NoSQL database. You plan to use the Azure Cosmos DB .NET SDK v3 API for NoSQL to upload the some files. You receive the following error message when uploading the files:  “413 Entity too large”. You need to determine which files you can upload to the Azure Cosmos DB for NoSQL database. Which files can you upload?

Solution: Max size of a file for uploading is 2MB
Explanation: [https://learn.microsoft.com/en-us/azure/cosmos-db/concepts-limits#per-item-limits](https://learn.microsoft.com/en-us/azure/cosmos-db/concepts-limits#per-item-limits)

Question 6 - Azure container instance and run-once task

You develop a Python application for image rendering. The application uses GPU resources to optimize rendering processes. You have the following requirements:  
– The application must be deployed to a Linux container.  
– The container must be stopped when the image rendering is complete.  
– The solution must minimize cost.  
You need to deploy the application to Azure. Which environment configuration values should you use? (To answer, select the appropriate values in the answer area.)

Solution: Azure Container Instances and Restart Policy
Explanation:  
Box 1: Azure Container Instances. Kubernetes can manage ACIs but is not a ‘compute target’ and it will increment the cost. The container instances in the group can access one or more NVIDIA Tesla GPUs while running container workloads such as CUDA and deep learning applications.  
[https://learn.microsoft.com/en-us/azure/container-instances/container-instances-gpu](https://learn.microsoft.com/en-us/azure/container-instances/container-instances-gpu)  
Box 2: Restart Policy. To stop the container after the execution (in fact is avoiding to restart it after a succeeded execution): set an appropriate restart policy for the container instance, depending on whether the command-line specifies a long-running task or a run-once task. For example, a restart policy of Never or OnFailure is recommended for a run-once task.  
[https://learn.microsoft.com/en-us/azure/container-instances/container-instances-start-command#command-line-guidelines](https://learn.microsoft.com/en-us/azure/container-instances/container-instances-start-command#command-line-guidelines)

Question 7 - Configure traffic splitting

A company uses Azure Container Apps. A container app named App1 resides in a resource group named RG1. The company requires testing of updates to App1. You enable multiple revision modes on App1. You need to ensure traffic is routed to each revision of App1. How should you complete the code segment? (To answer, select the appropriate values in the answer area.)

Solution: az containerapp ingress traffic set \
Explanation:  
[https://learn.microsoft.com/en-us/azure/container-apps/traffic-splitting?pivots=azure-cli](https://learn.microsoft.com/en-us/azure/container-apps/traffic-splitting?pivots=azure-cli)
Question 8 - Azure Container Registry (ACR) authentication case

You develop a containerized application. The application must be deployed to an existing Azure Kubernetes Service (AKS) cluster from an Azure Container Registry (ACR) instance. You use the Azure command-line interface (Azure CLI) to deploy the application image to AKS. Images must be pulled from the registry. You must be able to view all registries within the current Azure subscription. Authentication must be managed by Microsoft Entra ID and removed when the registry is deleted. The solution must use the principle of least privilege. You need to configure authentication to the registry. Which authentication configuration should you use? (To answer, select the appropriate values in the answer area.)

Solution: System-assigned managed identity and AcrPull
Explanation:  
– Registry Authentication Method: A System-assigned Managed Identity. It’s tied to the AKS service and automatically managed by Azure, aligning with the requirement for authentication to be managed by Microsoft Entra ID and removed when the registry is deleted. It adheres to the principle of least privilege as it’s specific to the AKS resource.  
– Registry Azure RBAC Role: The AcrPull role is the most fitting. It provides just enough permission to pull images from ACR, aligning with the principle of least privilege and meeting the requirement of the deployment process.

You are developing an Azure Function app. The Azure Function app must enable a WebHook to read an image from Azure Blob Storage and create a new Azure Cosmos DB document. You need to implement the Azure Function app. Which configuration should you use? (To answer, select the appropriate options in the answer area.)

Question 9 - Use case of deploying an Azure App Function

You are developing an Azure Function app. The Azure Function app must enable a WebHook to read an image from Azure Blob Storage and create a new Azure Cosmos DB document. You need to implement the Azure Function app. Which configuration should you use? (To answer, select the appropriate options in the answer area.)
![[Pasted image 20240508130952.png]]

Solution: http trigger for webhook, blob storage for reading image and azure cosmos db for document
Explanation:  
[https://learn.microsoft.com/en-us/azure/azure-functions/functions-bindings-storage-blob-input?tabs=python-v2%2Cisolated-process%2Cnodejs-v4&pivots=programming-language-csharp](https://learn.microsoft.com/en-us/azure/azure-functions/functions-bindings-storage-blob-input?tabs=python-v2%2Cisolated-process%2Cnodejs-v4&pivots=programming-language-csharp)  
[https://learn.microsoft.com/en-us/azure/azure-functions/functions-bindings-cosmosdb-v2-output?tabs=python-v2%2Cisolated-process%2Cnodejs-v4%2Cextensionv4&pivots=programming-language-csharp](https://learn.microsoft.com/en-us/azure/azure-functions/functions-bindings-cosmosdb-v2-output?tabs=python-v2%2Cisolated-process%2Cnodejs-v4%2Cextensionv4&pivots=programming-language-csharp)

Question 10 - 

You are developing several microservices named serviceA, serviceB, and serviceC. You deploy the microservices to a new Azure Container Apps environment. You have the following requirements:  
– The microservices must persist data to storage.  
– serviceA must persist data only visible to the current container and the storage must be restricted to the amount of disk space available in the container.  
– serviceB must persist data for the lifetime of the replica and allow multiple containers in the replica to mount the same storage location.  
– serviceC must persist data beyond the lifetime of the replica while allowing multiple containers to access the storage and enable per object permissions.  
You need to configure storage for each microservice. Which storage type should you use? (To answer, drag the appropriate storage types to the correct microservices. Each storage type may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.)