# Azure Fundamentals
 - https://aka.ms/az900

## Cloud Fundamentals
- What is Cloud computing 
![Cloud Compute](/assets/azure/1.png)
- Private Cloud
![Private Cloud](/assets/azure/2.png)
- Public Cloud
![public cloud](/assets/azure/3.png)
- Hybrid Cloud
  ![Hybrid](/assets/azure/4.png)
- CapEx vs OpEx
  ![Capex vs Opex](/assets/azure/5.png)

## Azure architecture and Azure compute services
  - Azure resources are components like storage, virtual machines, and networks that are available to build cloud solutions.
 - Resource Groups: A container to manage and aggregate resources in a single unit. Permission applied to RG applied to all resources contained in it. 
  ![RG](/assets/azure/6resourcegroups.png)

 - Azure Subscriptions provides authorization and authentication access to Azure accounts. 
    ![AS](/assets/azure/7azuresubscriptions.png)
    - Azure AD account is required to manage a subscription. 
    - Only one account admin is allowed. 
    - Merging of two subscriptions into a single is unallowed. 
    - resources can be moved to another subscription. 
 - Management Groups can include multiple azure subscriptions.![MG](/assets/azure/8managementgroups.png)
   - Subscriptions inherit conditions applied to MG. 

 - Availability Zones: 
   - Physically separte locations within an Azure region. 
   - Each AZ consists of one or more datacenters equipped with inddependent power, cooling and networking. 
   - if one AZ down, the other continue to work
   - Not all Azure regions support availabilty zones. 
   - AZ are different physical locations and will continue to work if the original data center fails.
   - AZ can be used to replicate data within the same region. 
 - Availabity Set protects Azure resources from failures within data center. 

- Azure Virtual Desktop
  - Enables you to use a cloud-hosted version of Windows. 
  - Separates OS, data and apps from local hardware
  - Supports both desktop and app virtualization runs on any devices or apps. 

- Azure Containers
  - Azure Containers are a light-weight, virtualized environment that does not require operating system management, and can respond to changes on demand.
  - Azure Container Instances: a PaaS offering that runs a container or pod of containers in Azure.
  - Azure Container Apps: a PaaS offering like container instances that can load balance and scale.
  - Azure Kubernetes Service: an orchestration service for containers with distributed architectures and large volumes of containers. Is a managed service for running Kubernetes in the cloud. 
  
- Virtural Machine
  - Virtural Machine are s/w emulation of physical computers.![VM](/assets/azure/9azurevm.png) 
   - VM Scale Sets provide LB opportunity to automatically scale resoruces. 
     - Scale out when resource needs high. 
     - Scale in when resource needs low. 
   - VM Availabilty Sets
   ![VM AS](/assets/azure/10azurevm-availabilitysets.png)
- Azure Container Services 
- Comparing Azure Compute Options
  ![Azure Compute Options](/assets/azure/11azure-computeoptions.png)

- Azure App Service: ![Azure App Service](/assets/azure/12Azureappservice.png)
  - Azure App Services is a fully managed platform to build, deploy, and scale web apps and APIs quickly.
  - PaaS offering with enterprise-grade performance, security, and compliance requirements.

- Azure Functions: 
  - A PaaS offers that support serverless compute options. Event-based code runs when called without requiring server infrastructure when incactive. 

## Azure networking
- Azure Vitual Network: Enables Azure resources to communicate with each other, over the internet, and on-premises network. 
![Azure VN](/assets/azure/13networkingservices.png)

- Network Security Groups: Filter n/w traffic b/w Azure resources in an Azure vitural network. 
  - To control the ports that users on the internet can use to access the VM.
  - NSG can be associated to VNet Subnet but not to VNet. 
  - NSG will not block all traffic by default. 
  - NSG always includes inbound and outbound security rules. 

- Azure Virtual Private Network Gateway: Sends encrypted traffic b/w an Azure VNet and an on-premises location over the public internet. ![Azure VPN Gateway](/assets//azure/14-azureVPN.png)
  - Funcution of site-to-site VPN: Provides a connection from an on-premises VPN device to an Azure VPN gateway. 
  
- Azure Express Route: Extends on-primises network into Azure over a private connection that is facilated by connectivity provider. ![Azure Express Route](/assets//azure/14-azureexpressroute.png)

- Azure DNS: Host DNS domains on global n/w of DNS name servers using Anycast networking. ![Azure DNS](/assets//azure/15-azureDNS.png)
- Futher reading on Site-to-Site VPN and Point=to-Site VPN connection. 

## Azure storage
Data is replicated three times within the primary region. 
- Storage Redundancy ![SR](/assets//azure/16-storagereduncy.png)
  - Three copies of data is maintained using locally redundant storage LRS
  - In Geo-redundent Storage, data is replicated synch three time on primary region, then replicated asynch to the secondary regions. 

- Azure Storage Services  ![SS](/assets//azure/17-datastorage.png)
  - Azure Blob: optimized for storing massive amounts of unstructured data, such as text or binary data.
    - Hot Tier: Optimized for storing data that is accessed frequently.
    - Cool Tier: Optimized for storing data that is infrequently accessed and stored for at least 30 days.
    - Cold: Optimized for storing data that is infrequently accessed and stored for at least 90 days.
    - Archive: Optimized for storing data that is infrequently accessed and stored for at least 180 days with flexible latency requirements.
  - Azure Disk: provides disks for virtual machines, applications, and other services to access and use.
  - Azure Queue: message storage service that provides storage and retrieval for large amounts of messages, each up to 64KB.
  - Azure Files: sets up a highly available network file share that can be accessed by using the Server Message Block protocol.
  - Azure Tables: provides a key/attribute option for structured non-relational data storage with a schema-less design.

- Azure File Management
  - Azure File Sync: 
    - Synchronizes Azure and on-premises Windows File Server in a bidirectional manner.
    - Cloud tiering keeps frequently accessed files local, while freeing up space
    - Rapid reprovisioning of failed local server (install and resync)
  - Azure Storage Explorer
    - Graphical user interface. Compatible with Windows,MacOS, and Linux. Uses AzCopy to handle file operations
  - AzCopy
    - command line utility, Copy blobs or files to or from your storage account. One-direction synchronization

- Azure Migrate
  - Unified migration platform for migration of servers and databases. 
  - Range of integrated and standalone tools

- Azure Data Box
  - Microsoft sends that we can store the data sends to MS to load all the data into the cloud. 
  - Stores upto 80TB of data. 
  - Migrate data out of Azure for compliance or regulatory needs.
  - Migrate data to Azure from remote locations with limited or no connectivity.
  - Move your disaster recovery backups to Azure.
  - Protect your data in a rugged case during transit.

## Azure identity, access, and security and Azure cost management
- Microsoft Entra ID:
  - Microsoft Azure’s cloud-based identity and accessmanagement service.
  - Athentication, SSO, Application management, Business to Business (B2B), Device management
  - An Entra ID tenant can have multiple subscriptions. 
  - An Azure subscription can only be associated with Microsoft Entra Tenant. 
  - Azure subscription expires, the assocaited Entra ID won't be deleted. 
- Microsoft Entra External ID B2B and B2C
  
- Conditional Access 
  - Used to bring signals together, to make decisions, and enforce organizational policies. Signal > Decision > Enforcement
  - User or Group membership. 
  - To ensure that only users located in a specific country can access Microsfot Entra integrated application, Conditional Access policy is applicable. 

- Role-based access control: Segregate duties within the teamand grant only the amount of access to users that they need to perform their jobs.Enables access to the Azure portal and controlling access to resources.

- Zero Trust: Protect assets anywhere with central policy
  
- Defense in Depth: A layered approach to securing computer systems. Provides multiple levels of protection. Attacks against one layer are isolated from subsequent layers
  - Pysical Security, Identify and Aceess, Perimeter, Network, Compute, Applicaiton, DAta. 

- Microsoft Defender for Cloud: is a free monitoring service that provides threat protection across both Azure and on-premises datacenters.
  - Provides security recommendations. Detect and block malware, 
  - Analyze and identify potential attacks, Just-in-time access control for ports
  - Enable just-in-tim(JIT) VM access with Microsfot defender for cloud. 


## Azure governance and compliance, Azure resource management, and Azure monitoring services
- Copying gigabytes of data to Azure from an on-premises n/w over a VPN, will incur no additional cost. 
- Copying gigabytes of data from Azure to an an on-premises n/w over a VPN, will incur additional cost. (ex of Outbound data transfers)
- Storage cost to be paid even after stopping Azure VM.
- Azure Reservations: committing to specific level of usage with discount percentage. 
- Data traffic b/w Azure services within the same region is always free. 

- Price Calculator: is a tool that helps you estimate the cost of Azure products. The options that you can configure in the Pricing Calculator vary between products, but basic configuration options include:
  - Region, Tier, Billing options, support options, program & offers, Azure dev/test pricing. 

- Total Cost Ownership Calculator: A tool to estimate cost savings you can realize by migrating to Azure. 
  - A report compares the costs of on-premises infrastructures with the costs of using Azure products and services in the cloud.
  - Azure subscription is not required to use TCO calculator. 

- Microsoft Cost Management: 
  - Can be used for budget alerts in Azure to send email alerts when cost exceeds a specific limit. 
  
- Tags: Provide metadata for Azure resources. Logically organizes resources into taxonomy. Consits of name/value pair. Useful for rolling-up billing information. 
  - Can be useful to generate billing reports separated that contain the Azure resource utilization for different offices of a company using Tags. 
  - Tags applied to a resource group or subscription aren't inherited by the resources it contains 

- Microsoft Purview:  is a family of data governance, risk, and compliance solutions that helps you get a single, unified view into your data. 
  - Brings insights about your on-premises, multi-cloud, and software-as-a-service data together.
  
- Resource Locks: Protect your Azure resources from accidental deletion or modification. 
  - Manage locks at subscription, resource group, or individual resource levels within Azure Portal.
  - Lock Types: Delete (Read/Update), ReadOnly (Read)
  - Azure resource inherit locks from its resource group , To modify a lock resource, the lock must be removed, An Azure resource can have multiple delete locks. 

### Managing and Deploying Resources

- Azure Portal
- Azure Cloud Shell: Interactive shell can be from any modern web browser. Bash or Powersheel options.

- Azure CLI: It's cross-platform can be used in Mac, Linux and Windows. 
  - Azure Powershell modules on any OS for managing Azure resources. 

- Azure Arc: Is a centralized management platform for multi-cloud, on-premises, and edge scenarios. 

- Azure Resource Manager (ARM): templates are JavaScript Object Notation (JSON) files that can be used to create and deploy Azure infrastructure without having to write programing commands.
  - ARM templates can be used to automate the creation of Azure resources. 
  
- Infrastructure as Code: Automate the setup process and ensure consistency in creating and maintaining cloud infra. Provides option in declarative way to manage changes. 
  - Ensure consistency in deployment across your cloud ecosystem.
  - Rapidly provision additional environments based on a standard configuration and build.
  - Manage configuration at scale.
  - To implement infrastructure as code for your Azure solutions, use Azure Resource Manager templates (ARM templates)

### Monitoring Tools

- Azure Advisor:  analyzes deployed Azure resources and makes recommendations based on best practices to optimize Azure deployments.
  - Use to Identify unused Azure VM or resources. 
  - Verify Azure subscription follows securtiy best practices

- Azure Service Health: is a collection of services that keep you informed of general Azure status, service status that may impact you, and specific resource status that is impacting you.
  - Azure Status: global view of the health of all Azure services across all Azure regions
  - Service Health: focused view on only the services and regions that you’re using. If a service is experiencing a problem in a region you’re not using, it won’t show up here
  - Resource Health: tailored view of your actual Azure resources. It provides information about the health of your individual cloud resources

- Azure Monitor:  maximizes the availability and performance of applications and services by collecting, analyzing, and acting on telemetry from cloud and on-premises environments.
  - Application Insights, Log Analytics, Smart Alerts, Automation Actions, Customized Dashboards. 

## Learn Guides
- Collection: https://learn.microsoft.com/en-ca/collections/o5met117w6pp01?ocid=cmms86x7u25