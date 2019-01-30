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
  - Resource group
    - A resource group is a method of grouping interdependent resources and services (i.e. VMs), web apps, DBs, and more for a given application and environment.
    - Think of it as a **folder**, a place to group elements of your app.
    - Allows you to easily manage and delete resources.
    - Enables you to monitor, control, access, provision, and manage billing for collections of resources. 
  - App Service plan
    - Set of physical resources and capacity available to deploy your App service apps into. 
    - **Web apps, mobile apps, azure functions, and API apps hosted in Azure App Service, all run in an App Service plan**
      - You can deploy unlimited number of applications into an App Service plan, the number you use greatly depends on the types of applications deployed.
      - Can use App Service plan to visualise CPU and memory utilization to help determine whether you need to scale or move applications into another App service plan.
    - Region (North Europe, West US etc)
    - Scale count (1, 2, 3 instances etc)
    - Instance size (small, med, large)
    - Pricing tier or SKU (free, shared, basic, standard, prem, premv2, and isolated)
      - Size of the VM that is going to host the application
    - Location
      - This field specifies the region where the App Service plan resides. i.e. where it will setup the VMs
  - Application Insights 
    - Monitoring and metric tools for performance of your apps.
    - Helps detect and diagnose quality issues in your web apps and web services, and helps you understand what your users actually do with it. 
    - Also enables you to view insight reports about traffic
- **Deployment slots**
  -  Add deployment slots to App Serivce web app. e.g. Staging deployment slot, production slot
  - You can easily swap the deployment slots so you can switch from staging to production etc.
- **Continuous integration/deployment support**
  - Azure portal provides out-of-the-box CI and deployment with the following:
    - Azure DevOps
    - GitHub
    - Bitbucket
    - Dropbox
    - OneDrive
    - or a local git repository on your dev machine.
  - Connect your web app to above, and App service will auto-sync code and any future changes on the code into the web app.
  - With Azure DevOps, you can define your own build and release process that compiles your source code, runs the tests, builds a release, and deploys the release into your web app everytime you commit.
- **Integrated Visual Studio publishing and FTP publishing**
  - Publish your web app to Azure via Web Deploy in Visual Studio or FTP.
  - FTP lacks some capability (better off not using it) 
- **Built-in auto scale support**
  - Can scale up/scale down the web app by increasing/decreasing the resources of the underlying machine that is hosting your web app.
  - Resources can be number of cores or the amount of RAM available.
  - Scaling out, on the other hand, is ability to increase number of machine instances that are running the web app.
- References
  - https://docs.microsoft.com/en-gb/learn/modules/host-a-web-app-with-azure-app-service/2-create-a-web-app-in-the-azure-portal
  - https://docs.microsoft.com/en-gb/learn/modules/host-a-web-app-with-azure-app-service/3-exercise-create-a-web-app-in-the-azure-portal?pivots=csharp
  - https://docs.microsoft.com/en-gb/learn/modules/host-a-web-app-with-azure-app-service/6-exercise-deploy-your-code-to-app-service?pivots=csharp

## Azure Load Balancer
- Load Balancer distributes new inbound flows that arrive on the Load Balancer's frontend to the backend pool instances, according to rules and health probes.
- Create load-balancing rules to distribute traffice that arrives at frontend to bakend pool instances. 
- A public Load Balancer can also provide outbound connections for VM's inside your virtual network by translating their private IP addresses to public IP addresses.
- Can be public Load Balancer or Internal Load Balancer
- Load Balancer  resource's functions expressed as a front end, a rule, a health probe, and a backend pool definition. You place VMs into the backend pool by specifying the backend pool from the VM.
- Benefits
  - Scale applications and create high availability for your services.
  - Supports inbound and outbound scenarios
  - Provides low latency and high throughput
  - Scales up to millions of flows for all TCP and UDP applications.
- **Why use Load Balancer?**
  - No downtime, as if one server (VM) fails, then you can reroute the traffic to the other servers (VMs)
  - Helps with finite resources, as TCP has limited connections, so by load balancing I can balance the traffic on different servers (VMs) and have higher availability. Can scale up and down etc. 
  - Load-balance incoming internet traffic to your VMs. Configuration is known as public load balancer.
  - Load-balance traffic across VMs inside a virtual network. Can also reach a Load Balancer FE from an on-premises network. Configuration is known as a internal load balancer.
  - Port forward traffic to a specific port on a VM.
  - Provide outbound connectivity for VMs inside your virtual network by using a public load balancer.
- Available in two tiers: Basic and Standard.
  - Differences in scale, features, and pricing.
  - Basic Azure Load Balancer is free of charge.
  - Load Balancer is not available with Basic Virtual Machines. 
  - Standard Balancer has prices associated to the number of rules (no charge if no rules are configured) and on the amount of data processed inbound and outbound irrespective of rule. 
    - https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-standard-overview
- **Concepts**
  - Public Load Balancer
    - Maps public IP address and port number of incoming traffic to the private IP address and port number of the VM, and vice versa for the response traffic from the VM.
    - Applying load-balancing rules enables distribution of specific types of traffic across multiple VMs or services. e.g. spreading load of web request traffic across multiple web servers
    - By default, Azure distributes network traffic equally among multiple VM instances. 
  - Internal Load Balancer
    - Directs traffic only to resources inside a virtual network or that use a VPN to access Azure infrastructure. 
    - Azure infrastructure restricts access to the load-balanced front-end IP addresses of a virtual network. 
    - FE IP addresses and virtual networks are never directly exposed to an internet endpoint.
    - The loadbalancer is only in the virtual network and not exposed to the public
- Reference
  - https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-overview
  - https://azure.microsoft.com/en-us/pricing/details/load-balancer/
  - https://docs.microsoft.com/en-us/azure/load-balancer/load-balancer-standard-overview

## Azure Virtual Network
- Enables Azure resources such as VM's to securely communicate with each other, the internet, and on-premises networks.
- Scoped to a single region; however multiple virtual networks from different regions can be connected using Virtual Network Peernig
- Provides isolation and segmentation
  - Each virtual network is isolated from other virtual networks
  - Specify custom private IP address space using public and private addresses. Azure assigns resources in a virtual network a private IP address from the address space that you assign.
  - Segment the virtual network into one or more subnets and allocate a portion of the virtual network's space to each subnet. 
- Communicate with on-premises resources with the following:
  - Point to site virtual private network (VPN)
  - Site to site VPN
  - Azure ExpressRoute
- Reference
  - https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview

## TODO:
2. CI/CD in azure
3. API apps 

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