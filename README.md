# Azure-Services
Introduction of Azure Services: 

1. Virtual Machine: A virtual machine (VM) is a software-based emulation of a physical computer, allowing multiple operating systems to run on a single physical host.
                    It uses a hypervisor to manage resources like CPU, memory, storage, and networking, isolating each VM for security and flexibility.

    -- Benefits: 
              Multi-OS Support: Run Linux on a Windows host, macOS on a PC, etc.
              Testing & Development: Experiment with software, OS versions, or configurations safely.
              Server Consolidation: Host multiple VMs (e.g., web server, database) on one physical server.
              Security: Isolate risky apps or malware for analysis.
              Portability: VMs can be saved as files, moved, or backed up.
              Cost Efficiency: Reduces need for multiple physical machines.

    -- Example Scenario:
             You’re a web developer with a Windows 10 laptop. You need to test a web application (e.g., a Python Flask app) on a Linux environment like Ubuntu,
             but you don’t have a second machine.Then you can use virtual machines available on cloud services.

   --Types of Virtual Machines (VMs):
               1. System Virtual Machines: These emulate a complete physical computer, including virtual CPU, memory, storage, and networking, allowing a full operating system
                                          (guest OS) to run on a host machine.It replicate the functionality of a standalone machine to run multiple OS environments on one physical device.
               2. Process Virtual Machine: These are designed to run a single application or process in an isolated, platform-independent environment, abstracting the underlying OS and hardware.
                                           It Provide a runtime environment for a specific program, shielding it from the host OS differences.

                                        

2.Azure Storage: It is a cloud storage service provided by Microsoft Azure. Azure Storage is a managed service for storing structured and      unstructured data in the cloud. It provides durability, scalability, and security, with features like encryption, access control, and redundancy options . It’s widely used for applications, backups, archiving, big data, and more.

----->Types of Azure Storage:

        a> Blob Storage: It Stores unstructured data like documents, images, videos, backups, and logs.
                Types:
                    Block Blobs: Ideal for large, discrete objects (e.g., images, videos, backups). Supports up to 5 petabytes of data.
                    Append Blobs: Optimized for append operations, perfect for logging or streaming data (e.g., log files).
                    Page Blobs: Used for random read/write operations, primarily for virtual machine disks (e.g., VHDs for Azure VMs).

                    Use Cases: Media storage, backups, static web content.
                    Features: Tiering options (Hot, Cool, Archive) for cost optimization based on access frequency.

        b> File Storage: It Provides fully managed file shares accessible via the SMB (Server Message Block) protocol or REST API.
                        It Acts like a  network file share, allowing multiple clients (e.g., apps, VMs) to access files simultaneously.

                        Use Cases: Shared file storage for applications, lift-and-shift of on-premises file shares, collaboration.
                        Features: Integrates with Azure Active Directory for access control, supports snapshots for backup.

        c> Table Storage:  A NoSQL key-value store for semi-structured data.
                            It Stores large amounts of data with flexible schemas, ideal for fast, simple queries using keys.
                    
                        Use Cases: Storing user data, metadata, configuration data, or lightweight analytics.
                        Features: Scalable, cost-effective, now often paired with Azure Cosmos DB Table API for enhanced capabilities.

        d> Queue Storage : It Enables reliable message queuing for asynchronous communication between application components.
                        It Stores millions of messages (up to 64 KB each) to decouple processes and ensure reliable delivery.
                        
                        Use Cases: Task scheduling, workload distribution, background processing (e.g., order processing in e-commerce).
                        Features: High throughput, simple REST-based access, message expiration options.

        e> Disk Storage : It Provides managed disks for Azure Virtual Machines.
                        It Offers persistent block storage as solid-state drives (SSD) or hard disk drives (HDD) for VMs.

                        Use Cases: VM storage, databases, big data workloads.
                        Features: Snapshots, encryption, and scalability.


-----> Key Features of Azure Storage: Scalability, Redundancy, Security, Access

-----> Choosing the Right Type of azure storage: 
            Unstructured Data: Use Blob Storage for files, images, or backups.
            File Sharing: Use File Storage for shared access across apps or users.
            Semi-Structured Data: Use Table Storage for key-value data.
            Messaging: Use Queue Storage for task queues or async processing.
            VM Storage: Use Disk Storage for virtual machine disks.



3. Azure Virtual Network (VNet): It is a fundamental component of Microsoft Azure, enabling secure, isolated networking in the cloud. 
                            It allows you to create a logically isolated section in Azure where you can deploy and manage resources like virtual machines (VMs), databases, and applications, mimicking a                                       traditional on-premises network but with the scalability and flexibility of the cloud.

---> Key Features: 
          Isolation: VNets provide a private, isolated environment for your Azure resources, ensuring they aren’t accessible from other networks unless configured.
          Customizable IP Addressing: You define private IP address ranges (IPv4 or IPv6) using CIDR notation (e.g., 10.0.0.0/16).
          Subnets: Divide a VNet into smaller segments (subnets) for organization, security, and traffic management.
          Connectivity: Connects Azure resources to each other, to on-premises networks, or to the internet.
          Security: Integrates with Network Security Groups (NSGs) for firewall-like rules, and supports Azure Firewall, DDoS protection, and private endpoints.
          Scalability: Scales seamlessly with your workload, supporting thousands of resources.
          Redundancy: Built on Azure’s global, highly available infrastructure.
---> Core Components: 
          -Address Space
          -Subnets
          -Routing
          -Network Security Groups (NSGs)
          -Connectivity Options
          -Internet Connectivity
              *VNet Peering: Connects two VNets (in the same or different regions) for low-latency, private communication.
              *VPN Gateway: Connects on-premises networks to Azure via a secure site-to-site or point-to-site VPN.
              *ExpressRoute: A private, high-bandwidth connection to Azure, bypassing the public internet.


---> Use Cases: 
          -Host Applications: Deploy VMs, app services, or Kubernetes clusters (via Azure Kubernetes Service) in a secure, isolated network.
          -Hybrid Cloud: Connect on-premises data centers to Azure for hybrid workloads using VPN or ExpressRoute.
          -Secure Communication: Isolate sensitive workloads and control traffic with NSGs, firewalls, and private endpoints.
          -Scalable Infrastructure: Support multi-tier apps (e.g., web, app, and database tiers) in separate subnets.
          -Disaster Recovery: Replicate resources across regions with VNet peering or geo-redundant setups.



4. Azure SQL Database: It is a fully managed, platform-as-a-service (PaaS) relational database service within the Azure SQL family, built on Microsoft SQL Server. It provides a scalable, secure, and highly available cloud database solution, eliminating the need for manual infrastructure management like patching, backups, or server maintenance. It’s ideal for modern cloud applications and supports relational data, JSON, spatial, and XML formats.

--->Key Features: 
        *Scalability
        *Serverless
        *High Availability
        *Security
        *Performance (Automatic tuning (e.g., index creation, query optimization)).
        *Management
        *Connectivity:

--->Deployment Options :
        *Single Database: A standalone database with dedicated resources.
                        Ideal for apps needing a single, isolated database (e.g., a small web app).
        *Elastic Pool: A collection of databases sharing a pool of resources (compute, memory, etc.).
                        Cost-effective for multiple databases with variable workloads (e.g., SaaS applications).

--->Purchasing Models :
        -DTU-Based Model : Database Transaction Units (DTUs) bundle CPU, memory, and I/O.
            Tiers: Basic, Standard, Premium

        -vCore-Based Model: Choose virtual cores, memory, and storage independently.
            Tiers: General Purpose, Business Critical, Hyperscale

        -Serverless : Auto-scales compute based on demand, pauses during inactivity.
            Billed per second, ideal for unpredictable workloads.

---> Use Cases: 
        -Web and Mobile Apps: Host databases for e-commerce, blogs, or mobile backends.
        -Transactional Systems: Support CRM, ERP, or financial applications.
        -Business Intelligence: Integrate with tools like Power BI for reporting.
        -Development and Testing: Rapidly provision databases for dev/test environments.
        -Multi-Region Apps: Use geo-replication for global availability and low latency.

---> Key Considerations
        -Performance Tier
        -Cost
        -Size Limits
        -Networking
        -Migration


5. Azure function: It is a serverless compute service provided by Microsoft Azure, allowing you to run event-driven code without managing servers. 
                    It enables you to execute small pieces of code (functions) in response to triggers, scaling automatically to handle demand.
                    It’s ideal for building lightweight, cost-efficient applications or automating tasks in the cloud.

---> Key Features: 
            -Serverless: No server management; Azure handles infrastructure, scaling, and maintenance.
            -Event-Driven: Functions execute in response to triggers like HTTP requests, timers, or messages from other Azure services.
            -Scalability:Automatically scales out based on workload.
            -Durability: High availability and reliability, backed by Azure’s global infrastructure.
            -Bindings: Simplify integration with inputs (e.g., read from storage) and outputs (e.g., write to a queue) via declarative configurations.

---> Pricing Models:
            Consumption Plan: Pay-per-execution, billed by compute time and memory usage; scales to zero when idle.
            Premium Plan: Pre-warmed instances for low latency, VNet support, and longer execution times.
            App Service Plan: Run on dedicated VMs with fixed costs, shared with other App Services.

---> Language Support: Write functions in C#, Java, JavaScript, TypeScript, Python, PowerShell, and more.




6. Azure Terraform: It is an open-source Infrastructure as Code (IaC) tool by HashiCorp that lets you define, provision, and manage Azure infrastructure using declarative configuration files written in HashiCorp Configuration Language (HCL) or JSON. With Terraform, you can automate the deployment of Azure resources—such as virtual machines, networks, storage, databases, and more—in a consistent, repeatable, and version-controlled manner. The Azure Provider for Terraform (azurerm) integrates with Azure Resource Manager (ARM) to create, update, and delete resources in your Azure subscription.

---> Why Use Terraform with Azure?
            
            -Automation: Deploy complex Azure environments quickly without manual intervention.
            -Consistency: Ensure identical setups across dev, test, and prod environments.
            -Version Control: Store infrastructure code in Git, track changes, and collaborate.
            -Modularity: Use reusable modules for common patterns (e.g., VNet, VM setups).
            -Multi-Cloud: Manage Azure alongside AWS, GCP, or other providers in one workflow.
            -Idempotency: Terraform applies only necessary changes, avoiding duplication.
            -Cost Management: Define resources precisely to avoid over-provisioning.
