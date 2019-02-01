# Azure 

## Security 
- Read this or do the module: 
  - https://docs.microsoft.com/en-gb/learn/modules/design-for-security-in-azure/2-defense-in-depth
  - https://docs.microsoft.com/en-gb/learn/modules/design-for-security-in-azure/8-summary
- **Top 5 security items to consider before publishing to production**
  1. Activate Azure Security Center
  2. Validate and verity application inputs and outputs (Mainly User)
    - **Always validate every input for your application**
    - Always use whitelist approach: only accept "known good" input
      - https://docs.microsoft.com/en-gb/aspnet/web-pages/overview/ui-layouts-and-themes/validating-user-input-in-aspnet-web-pages-sites
      - https://www.owasp.org/index.php/Input_Validation_Cheat_Sheet
    - **Always use parameterized queries, do not concat query strings together as this enables SQL injection.**
      - https://stackoverflow.com/questions/60174/how-can-i-prevent-sql-injection-in-php
    - **Always encode your ouput to prevent XSS**
      - Any output presented visually or within a document should always be encoded and escaped. (to prevent XSS)
      - In ASP.NET all output is already encoded.
    - Sanitize and validate inputs
    - https://docs.microsoft.com/en-gb/learn/modules/top-5-security-items-to-consider/3-inputs-and-outputs
  3. Store secrets in Azure Key Vault
    - Storing confidential items like connection strings, security tokens, certificates, and passwords in code is a security risk. 
    - Even storing this data in web config is a bad idea - you allow anyone who has access to source code or web server access to your privdate data. 
  4. Ensure you are using the latest version of your framework and using its security features
    - Awlays use built-in security features, and keep them up to date.
    - Azure Security Center will warn you if your frameworks are out of date as part of recommendations tab.
  5. Verify your program dependencies and libraries are safe to use
    - https://docs.microsoft.com/en-gb/learn/modules/top-5-security-items-to-consider/6-safe-dependencies
- Azure Security Center
  - Azure Security Center (ASC) is a monitoring service providing thread protection on all your services both in Azure and on-premises.
    - Provides security recommendations
    - Monitors security settings across on-premises and cloud workloads
    - Monitor all services and perform automatic security assessments to potential vulnerabilities
    - Uses Machine learning to block malware from being installed
    - Identify potential inbound attacks 
    - Just-in-time access control for ports, reducing your attack surface by ensuring the network only allows traffic you require.
  - **Activate Azure Security Center**
    - In Azure portal > Security center or Azure security center > Policy and Compliance > Coverage
    - It has free tier and standard tier. 
- **Azure Key Vault**
  - A secret store: centralized cloud service for storing application secrets
  - Keeps confidential data safe by keeping application secrets in a single central location and providing secure access, permissions control, and access logging.
  - Secrets stored in individual vaults, each with own config and security policy. 
  - Can get data through REST API or through a client SDK.
  - Designed to store configuration secrets for server applications NOT for storing data belonging to app's users. 
- Reference
  - https://docs.microsoft.com/en-gb/learn/modules/top-5-security-items-to-consider/1-introduction
  - https://docs.microsoft.com/en-gb/learn/modules/design-for-security-in-azure/2-defense-in-depth

## Azure Kubernetes Services (AKS)
- **Kubernetes**
  - A standard way to manage application containers in production environment.
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

## Azure App Service
- PaaS - You focus on the build while Azure takes care of the ifnrastructure to run and scale your apps.
- Azure App Service is a fully managed cloud computing platform within the Azure environment that is optimized for hosting web apps, REST APIs, and mobile backends.
  - Supports code written in .NET, .NET Core, Java, Ruby, Node.js, PHP, and Python.
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
    - Can continue to add apps to an existing plan but they will share the same resource. Overloading an App Service plan can cause reduced performance or downtime for your new and existing apps.
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

## Integrate on-premises Active Directory domains with Azure Active Directory
- https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/identity/azure-ad
## Create VPN gateway connection from on-premises network to the VNet 
- https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-howto-site-to-site-resource-manager-portal

## Azure Virtual Network
- Enables Azure resources such as VM's to securely communicate with each other, the internet, and on-premises networks.
- Scoped to a single region; however multiple virtual networks from different regions can be connected using Virtual Network Peering
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

## Continuous Integration/Continuous Delivery (CI/CD)
- https://docs.microsoft.com/en-us/azure/app-service/deploy-continuous-deployment?toc=%2fazure%2fapp-service%2fcontainers%2ftoc.json
- **Azure pipelines**
  - 

## Azure Cosmos DB
- Azure Cosmos DB is Microsoft's properiety globally-distributed, multi-model database service
- Database as a Service
- NoSQL database
  - It is not a relational database and is not good with relational data
  - Not good at JOINS
- Multi-model as in it supports:
  - key-value
  - Document
  - graph
  - Column-family
- By default, you can interact with Cosmos DB using SQL API. All available API's available are:
  - SQL (document)
  - MongoDB (document)
  - Cassandra
  - Azure Table
  - Gemlin (graph)
  - Note: these are just API's that allow you to interact with Cosmos DB.
- This also makes migrating existing MongoDB apps to Cosmos DB easily etc.
- Manages data at planet-scale
- Schema-agnostic
- Azure Cosmos DB provides client-side SDKs for: 
  - .NET, 
  - .NET Core, 
  - Java, 
  - Node.js
  - Python
- Horizontally scales
- **Data model**
  - Stores "items" in "containers"
  - Containers are grouped in "databases", which are same as namespaces.
  - Containers are schema-agnostic, there is no schema when adding items.
  - Every field in each item is automatically indexed.
- **Use case**
  - If your data changes a lot
  - If your data is being ingested at high speed
  - If there lots of data (peta-bytes etc).
  - As long as you do not need JOINS.
- There is a extension for Visual Studio Code you do not have to go to Azure portal to create a DB.
- **Note:** 1000 request units per second (RU/s). 1000 is the minimum RU/s value you can set to enable automatic scaling.
- References
  - https://docs.microsoft.com/en-us/azure/cosmos-db/mongodb-introduction
  - https://docs.microsoft.com/en-us/azure/cosmos-db/introduction
  - https://docs.microsoft.com/en-gb/learn/modules/create-cosmos-db-for-scale/2-create-an-account
  - https://docs.microsoft.com/en-gb/learn/modules/create-cosmos-db-for-scale/3-what-is-a-request-unit
## Azure Service Fabric
- Build and operate always-on, scalable, distributed apps
- **Designed for large and complex microservice systems.**

## Containers
- Docker containers can be hosted in your own Linux or Windows infrastructure
- Docker containers can be hosted in cloud services such as:
  - **Azure Container Service**
    - Can manage, orchestrate, and scale container-based applications in the cloud.

## Serverless Compute 
**Serverless logic**
  - Serverless computing: your cloud provider manages the provisioning and maintenance of the infrastructure letting you focus completely on building the app logic. 
  - Enables you to run pieces of code or functions, written in the programming language of your choice, in the cloud.
- **Serverless compute**
  - Thought of as function as a service (FaaS), or a microservice hosted in the cloud
  - Business logic runs as functions and you don't have to manually provision or scale infrastructure.
  - Cloud provider manages infrastructure
  - App is automatically scaled out or down depending on the load
  - The two most common approaches are:
    - Azure Logic Apps
    - Azure Functions

## Azure Functions (Serverless)
- Azure functions is a serverless application platform. 
- Can host business logic that can be executed without provisioning infrastructure.
- Provides scalability and only charged for the resources used. 
- event driven
- compute-on-demand and scale-based 
- Enables creation of HTTP-based API endpoints accessible by a wide range of applications, mobile, IoT devices etc.
- can implement code that is triggered by events occuring in Azure or third party service as well as on-premises systems.
- Allows developers to take action by connecting to data sources or messaging solutions thus making it easy to process and react to events.
- Basically like a Web API endpoint but it costs money everytime you use it.
- **Defintions**
  - What is a Function app?
    - functions are hosted in an execution context called a function app.
    - You define function apps to logically group and structure your functions and compute resource in Azure. 
    - **Must be linked to a storage account**
- **Securing HTTP triggers**
  - By default, it's set to "Function" which requires a API key
  - It can also be set to "Admin" to use a global "master" key
  - Can be anonymous to indicate no key is required.
  - You can also change the authorization level through the function properties after creation.
  - Since we specified "Function" when we created this function, we will need to supply the key when we send the HTTP request. 
    - You can send it as a query string parameter named code, or as an HTTP header (preferred) named x-functions-key.
  - Functions can integrate with other services, like Event Grid, GitHub, Twilio, Microsoft Graph, and Logic Apps to create complex and robust serverless workflows quickly and easily.
- Plans
  - **Consumption plan (Serverless)**
    - Used when using Azure serverless application platform.
    - Provides automatic scaling and bills you when your functions are running
    - Comes with default config timeout period of 5 mins, up to 10 mins.
  - **Azure App Service plan (Not serverless)**
    - Avoids timeout periods by having functions run continously on a VM
    - Responsible for managing the app resources the function runs on
- **Test your Azure function** 
  - Manual execution
    - If HTTP trigger, you can use Postman or cURL to initiate an HTTP request, which is available from the HTTP trigger definition (Get function URL)
  - Testing in the Azure portal
    - Test > Run in Azure Portal
- **Benefits**
  - Hosts business logic code in the cloud
  - Automatic scaling
  - No servers to maintain or manage, also avoids over-allocation of infrastructure
  - Only changed for what you use - not on reserved time.
  - **Functions**
    - Stateless logic: function instances are created and destroyed on demand. If state is required, it can be stored in associated storage service.
    - Event driven: they run only in response to an event.
    - Functions can be used in traditional compute environments.
- **Triggers**
  - Azure Functions supports triggers which are used to determine how an Azure function is executed.
- **Bindings**
  - A binding is a connection to data within your function.
  - They are optional and come in form of input and output bindings.
  - An input binding is the data your function receives.
  - An output binding is the data your function sends
  - Unlike a trigger, a function can have multiple input and output bindings
- Support for Azure Function Triggers:
  - https://docs.microsoft.com/en-gb/learn/modules/create-serverless-logic-with-azure-functions/4-creating-and-executing-an-azure-function
- **Drawbacks of serverless compute solution**
  - Execution time
    - by default, functions have a timeout of 5 minutes, the max is 10 mins. If requires more, then can host on VM. Durable functions also exist to allow you to orchestrate the executions of multiple functions without any timeout.
  - Exceution frequency
    - If you expect your function to be executed continuously by multiple clients, it would be prudent to estimate the usage and caculate the cost of using functions accordingly. It might be cheaper to host on a VM.
    - While scaling, only 1 function app instance can be created every 10 seconds, for up to 200 total instances. 
- **Serverless APIs using Azure Functions**
  - **Azure Functions Proxies**
    - Allows you to forward requests to other resources.
    - You define HTTP endpoint just like with HTTP trigger, but instead of writing code to execute when that endpoint is called, you provide a URL to a remote implementation
    - Allows to compose multiple API sources into a single API surface
    - Useful for building your API as microservices
    - A proxy can point to any HTTP resource, such as:
      - Azure Functions
      - API apps in Azure App Service
      - Docker containers in App Service in Linux
      - Any other hosted API
- **Summary **
  - **Azure functions is code is being triggered by an event**
  - Can be developed and debugged on local workstation, which is a big plus to increase developer productivity
  - When dealing with synchronous request/response calls, that execute more complex logic, Azure function is the preferred option
- **Supports**
  - Continous deployment and integration
  - Intuitive browser-based user interface allowing you to create scheduled or triggered pioeces of code implemented in a variety of programming languages.
- Data processed by Azure Functions can persist into Azure data services such as Azure storage, Azure SQL DB, and Document DB.
- References
  - https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview
  - https://docs.microsoft.com/en-gb/learn/modules/create-serverless-logic-with-azure-functions/2-decide-if-serverless-computing-is-right-for-your-business-need
  - https://docs.microsoft.com/en-us/azure/azure-functions/functions-create-serverless-api

## Azure Logic Apps (Serverless)
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
  - Instead, Azure AD is partitioned into separate tenants.
  - A tenant is a dedicated, isolated instance of the Azure AD servicve, owned and managed by an organization.
  - When you sign up for a Microsoft cloud service subscription such as Microsoft Azure or Office 365, a dedicated instance of Azure AD is automatically created for your organization.
- Azure AD is not the same as Windows Active Directory. Windows Active Directory is focused on securing Windows desktops and servers. In contrast, Azure AD is all about web-based authentication standards such as OpenID and OAuth.
- Can take avantage of Azure Key Vault to store your application secrets. 
- Managed Service Identity for Azure couples your app to Azure Active Directory and injects credentials into your application without having to store them in your config files or anywhere else.
- https://azure.microsoft.com/en-au/blog/get-the-azure-quick-start-guide-for-net-developers/