# AZ-204: Developing solutions for Microsoft Azure

## About
Microsoft Azure Developers design, build, test and maintain cloud solutions, such as applications and services, partnering with cloud solution arch, cloud DBA's, cloud administators, and clients to implement these solutions. 
- [Developing Solutions for Microsoft Azure](https://aka.ms/CourseAZ-204)
- [Microsoft Certified: Azure Developer Associate](https://learn.microsoft.com/en-us/credentials/certifications/azure-developer/?practice-assessment-type=certification)

## 1. Implement Azure App Service Web Apps. 

### Azurre App Service
- HTTP-based service for web app hosting, REST API
- Built-in scale support (Scaling, Scale Out/In manually/auto)
- CICD (Azure Devops, GitHub, Bitbucket, FTP)
- Deployment slots (Targe deployments to test or prod envs, customize what settings are swapped b/w slots)
- Select App Service Plan (Free, Dev (Win only), Basic, Standard, Premium)
  - Free & Dev > Shared and Minumum compute, Not a Prod-ready. 
  - [App Service Pricing](https://azure.microsoft.com/en-us/pricing/details/app-service/windows/)
- [Automatic Scaling: Azure Web Apps Unleash Their Hidden Potential](https://techcommunity.microsoft.com/t5/apps-on-azure-blog/automatic-scaling-azure-web-apps-unleash-their-hidden-potential/ba-p/4130820)  

  
## 2. Implement Azure Functions. 
- [Triggers and bindings in Azure Functions](https://learn.microsoft.com/en-us/azure/azure-functions/functions-triggers-bindings?tabs=isolated-process%2Cpython-v2&pivots=programming-language-javascript)
- [](https://pyroller.azurewebsites.net)
- [Pricing Functions](https://azure.microsoft.com/en-us/pricing/details/functions/)
- [Develop Azure Functions locally using Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Cisolated-process%2Cnode-v4%2Cpython-v2%2Chttp-trigger%2Ccontainer-apps&pivots=programming-language-csharp)
- Azure Blob storage is MS object storage solution for the cloud. Optimized for storing massive amounts of unstructured data. 
  - Serving images or docs directly to a browser
  - storing files for distributed access
  - Steaming video/audio
  - Writing to log files
  - Storing data for backup and restore, disaster recovery, and archiving. 
  - Storing data for analysis by an on-premises or Azure-hosted service
- Built on a unified Distributed storage system. (Files, Blobs, Tables & Queues)
- Types of Blobs
  - Block blobs: Sequential file I/O >
  - Page blobs:Random-write pattern data > VMs Dsks, VHDs
  - Append blobs: For logs. 
  - [Understanding block blobs, append blobs, and page blobs](https://learn.microsoft.com/en-us/rest/api/storageservices/understanding-block-blobs--append-blobs--and-page-blobs)
  - [Util - Serilog.Sinks.AzureBlobStorage](https://github.com/chriswill/serilog-sinks-azureblobstorage)


## 3. Develop solutions that use Blob Storage
- [Reliable web app pattern for .NET - Plan the implementation](https://learn.microsoft.com/en-us/azure/architecture/web-apps/guides/reliable-web-app/dotnet/plan-implementation)
- [Per-app scaling for high-density hosting - Azure App Service](https://learn.microsoft.com/en-us/azure/app-service/manage-scale-per-app)

## 4. Develop Solutions that use Azure Cosmos DB
- [Common use cases and scenarios for Azure Cosmos DB](https://learn.microsoft.com/en-us/azure/cosmos-db/use-cases)
- [Microsoft Customer Story-Rockwell Automation goes cloud-native on Azure to bring modern software development paradigms to the factory floor](https://customers.microsoft.com/en-us/story/1687814927656339280-rockwell-automation-azure-discrete-manufacturing-usa)
- [Microsoft Customer Story-SdNcenter and Ascensia deliver online diabetes support globally with Azure](https://customers.microsoft.com/en-us/story/1751639840626325813-sdncenter-healthcare-azure-en-poland)
- [Model and partition data with a real-world example - Azure Cosmos DB for NoSQL](https://learn.microsoft.com/en-us/azure/cosmos-db/nosql/model-partition-example)
  
## 5. Implement Containerzied solutions
- Manage container images in Azure Container Registry
- Run container images in Azure Container Instances
- Implement Azure Container Apps: 
- [KEDA | Kubernetes Event-driven Autoscaling](https://keda.sh/)
- [AZ-2003: Deploy cloud-native applications using Azure Container Apps](https://github.com/MicrosoftLearning/az-2003-deploy-cloud-native-applications-using-azure-container-apps)
- [Practicals](https://github.com/rob-foulkrod/BeyondBasics)
## 6. Implement User Authentication and Authorization

## 7. Implement Secure Cloud solutionss

## 8. Implement API managemenet 
  - [Policies in Azure API Management](https://learn.microsoft.com/en-us/azure/api-management/api-management-howto-policies)
  - [Azure API Management policy reference](https://learn.microsoft.com/en-us/azure/api-management/api-management-policies)

## 9. Develop event-based solutions
- [Azure Event Hubs Event Processor client library for .NET](https://github.com/Azure/azure-sdk-for-net/blob/main/sdk/eventhub/Azure.Messaging.EventHubs.Processor)
- [Definitions: Messaging or eventing infrastructure](https://github.com/clemensv/messaging?tab=readme-ov-file#definitions-messaging-or-eventing-infrastructure)
- [Azure Service Bus trigger for Azure Functions](https://learn.microsoft.com/en-us/azure/azure-functions/functions-bindings-service-bus-trigger?tabs=python-v2%2Cisolated-process%2Cnodejs-v4%2Cextensionv5&pivots=programming-language-csharp)

## 10. Develop message-based solutions. 
- [Events, Data points and Messages](https://www.youtube.com/watch?v=ITrlLErsqzY&feature=emb_imp_woyt)

## 11. Trobleshoot solutions by using Application Insights
- [Monitor Node.js services with Application Insights - Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/app/nodejs)


## 12. Implement Caching for solutions. 

## Exam Related
- [https://aka.ms/courseaz-204](https://aka.ms/courseaz-204)
- [Free exams and practice tests](esi.microsoft.com/getcertification)
- [Free Azure analyst reports, e-books, and white papers](https://azure.microsoft.com/resources/whitepapers/?wt.mc_id=esi_mtt_content_wwl)
- [Microsoft Learn exam readiness](https://aka.ms/ExamReadinessZone?wt.mc_id=esi_mtt_content_wwl)- [Preparing for exams using resources in the Learner Experience Portal](https://aka.ms/LxPExamReadinessVideo)
- [Enterprise Skills Initiative: The Learner Experience Portal overview](https://aka.ms/LxPOverviewVideo)
- [Registering for Microsoft Virtual Training Days in the ESI Learner Experience Portal](https://aka.ms/LxPRegisterVTDVideo)
- [Scheduling a Microsoft Certification exam in the ESI Learner Experience Portal](https://aka.ms/LxPScheduleExamVideo)
- [Registering for a Microsoft-delivered course in the ESI Learner Experience Portal](https://aka.ms/LxPRegistrationClassVideo)
- [https://ncv.microsoft.com/5W4yPHUzmp](https://ncv.microsoft.com/5W4yPHUzmp)