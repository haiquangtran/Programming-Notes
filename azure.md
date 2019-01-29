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
