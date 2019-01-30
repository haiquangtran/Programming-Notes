# Azure 

## Azure Kubernetes Services (AKS)
- **Kubernetes**
  - A standward way to manage application containers in production environment.
- Azure Kubernetes Services brings Azure and Kubernetes together, allowing users to quickly create fully managed Kubernetes clusters.

## Azure vs AWS
- **Azure**
  - PaaS (Platform as a service), IaaS
    - You do not have to maintain VMs yourself (security, service packs etc), just have to maintain your application code.
  - Built-in load balancing abilities
  - .NET written applications moved to the cloud fairly easily.
  - **Compute power**
  - Users choose Virtual Hard Disk (VHD), which is equivalent to a Machine instance, to create a VM. 
    - VHD can be pre-configured.
  - **Storage**
    - Offers temporary storage through D drive, 
    - Block storage: Page Blobs for Vms.
    - Object storage: Block blobs and Files
    - Supports relational databases, NoSql and big Data through Azure Table and HDInsight.
    - Offers site recovery
    - Import/export and azure backup for additional archiving and recovery options.
  - http://www.onlinetech.com/resources/references/aws-vs-azure-key-differences
- **AWS**
  - IaaS
    - Manages the Data, runtime, middleware, operating system, applications.
  - Tools are mostly at a very low level.
  - AWS - Amazon Elastic Computer Cloud (EC2): a web service that lets you assign your application to as many "compute units" as desired.
  - **Compute power**
    - Users can configure their own VMs or choose pre-configured machine images (or customise MIs)
    - Users choose size, power, memory capacity, and number of VMs, and choose from different regions and availability zones.
  - **Storage**
    - has temporary storage that is allocated once an instance is started and destroyed when the instance is terminated.
    - Provide block storage (same as hard disks), that can be separate or attached to an instance
    - Object storage is offered with S3
    - Fully supports relational and NoSQL databases and Big Data.
  - Amazon's platform basic advantage is simple: You can just use the amount of storage you want, when you want it.
  - https://www.infoq.com/news/2008/11/Comparing-EC2-App-Engine-Azure

## Azure
- Enables you to quickly and efficiently build, deploy, monitor and scale cloud hosted solutions. 
- Deployment model is flexible:
  - Can use multiple IDE's to deploy etc.
- 

## Azure App Service
- PaaS - You focus on the build while Azure takes care of the ifnrastructure to run and scale your apps.
- Azure App Service is a fully managed cloud computing platform within the Azure environment that is optimized for hosting web apps, REST APIs, and mobile backends. 
  - Cloud hosting service for your app
- Hosting your web application using Azure App Service makes deploying and managing a web app easier compared to managing a physical server
- **How to host your application on Azure App Service**
  - You can create a web app using the Azure portal, the Azure CLI, a script, or an IDE.
  - By creating a web app in the Azure portal, you are creating a set of hosting resources in App Service, which you can use to host any web-based application that is supported by Azure. 
- Good choice for **Stateless microservices**
- **Definitions**
  - Resource group: 
  - Application Insights: monitoring and metric tools for performance of your apps.
- **Deployment slots**
  -  Add deployment slots to App Serivce web app. e.g. Staging deployment slot, production slot
  - You can easily swap the deployment slots so you can switch from staging to production etc.
- Reference
  - https://docs.microsoft.com/en-gb/learn/modules/host-a-web-app-with-azure-app-service/2-create-a-web-app-in-the-azure-portal



## Creating a pipeline
- **Azure pipelines**
  - 

## Cosmos DB
- Azure Cosmos DB is Microsoft's properiety globally-distributed, multi-model database service
- NoSQL database
- Manages data at planet-scale
- Schema-agnostic
- Horizontally scales
- **Data model**
  - Stores "items" in "containers"
  - Containers are grouped in "databases", which are same as namespaces.
  - Containers are schema-agnostic, there is no schema when adding items.
  - Every field in each item is automatically indexed.

## Azure Service Fabric
- Build and operate always-on, scalable, distributed apps
- **Designed for large and complex microservice systems.**

## Containers
- Docker containers can be hosted in your own Linux or Windows infrastructure
- Docker containers can be hosted in cloud services such as:
  - **Azure Container Service**
    - Can manage, orchestrate, and scale container-based applications in the cloud.

## Azure Functions
- event driven
- compute-on-demand and scale-based 
- Enables creation of HTTP-based API endpoints accessible by a wide range of applications, mobile, IoT devices etc.
- can implement code that is triggered by events occuring in Azure or third party service as well as on-premises systems.
- Allows developers to take action by connecting to data sources or messaging solutions thus making it easy to process and react to events.
- Basically like a Web API endpoint but it costs money everytime you use it.
### Summary
- **Azure functions is code is being triggered by an event**
- Can be developed and debugged on local workstation, which is a big plus to increase developer productivity
- When dealing with synchronous request/response calls, that execute more complex logic, Azure function is the preferred option
## Supports
- Continous deployment and integration
- Intuitive browser-based user interface allowing you to create scheduled or triggered pioeces of code implemented in a variety of programming languages.
- Data processed by Azure Functions can persist into Azure data services such as Azure storage, Azure SQL DB, and Document DB.
- https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview

## Azure Logic Apps
-  Simplifies how you build automated scalable workflows that integrate apps and data across cloud services and on-premises systems.
- Create, design, and deploy logic apps that automate business processes
### Summary
- **Logic apps is a work flow triggered by an event**
- Logic apps run only in the cloud, as it has dependency on Microsoft managed connectors. It cannnot be debug, test or run Logic apps locally
- Logic apps better suited for asynchronous integration and fire-and-forget messaging that requires reliable processing.

## Azure Active Directory (AD)
- Can use for storing user identities and doing authentication and authorization.
- Azure AD is a modern identity provider that supports multiple authentication protocols to secure applications and services in the cloud.
  - Users, applications, and other entities registered in Azure AD aren't all lumped into a single global service.
  - Insetad, Azure AD is partitioned into separate tenants.
  - A tenant is a dedicated, isolated instance of the Azure AD servicve, owned and managed by an organization.
  - When you sign up for a Microsoft cloud service subscription such as Microsoft Azure or Office 365, a dedicated instance of Azure AD is automatically created for your organization.
- Azure AD is not the same as Windows Active Directory. Windows Active Directory is focused on securing Windows desktops and servers. In contrast, Azure AD is all about web-based authentication standards such as OpenID and OAuth.
- Can take avantage of Azure Key Vault to store your application secrets. 
- Managed Service Identity for Azure couples your app to Azure Active Directory and injects crednetials into your application wihtout having to store them in your config files or anywhere else.
- https://azure.microsoft.com/en-au/blog/get-the-azure-quick-start-guide-for-net-developers/