# Azure Compute
## Virtual Machines (VMs)
VMs are considered **IaaS** - manange everything except the hardware
- OS
- Applications to install
- How to maintain it
- How much CPU, RAM, etc.

Use the **Azure Portal** to deploy and manage VMs  
Use **Azure Blueprints** to ensure compliance on VMs  
Use **Azure Recommendations** to ensure better security and performance
Use **Azure Tools** to add functionality to a VM, such as monitoring, diagnostics, etc.

### Pricing
More CPU, memory, or GPU costs more money

Virtual machines run all the time, unless a schedule is setup

## Scale Sets
Dynamically increase and decrease identical VMs as needed for a particular application

Autoscaling can be triggered off metrics, such as CPU and memory utilization or a schedule

Ensures that the business can be nimble as demand increases but also controls costs in times that utilization is lower

## App Services
**PaaS** model

Various services in which the hardware and virtual infrastructure does not need to be maintained

### Web Apps
Upload code and have it run on a highly avaialable system.  Very similar to AWS Elastic Beanstalk

Runs Windows and Linux

Supports for many languages
- .NET
- Java
- Node.js
- PHP
- Python
- Ruby

Autoscaling and load balancing baked in

### Web Apps for Containers
Similar to **Web Apps** but instead of running on a VM, the code will be containerized

Useful if there is already a pre-existing container that will be used

### API Apps
Very similar to **Web Apps**, except better integrations for APIs

Can use existing API code (using Swagger, WADL, other langusages) and deploy it without managing  
The code that runs the API can be main languages, such as C#, Python, PHP, Java

Note there is another similar service called **API Management**, which allows multiple APIs to be exposed using a single gateway

## Container Instances
**PaaS** model

**Azure Container Instance (ACI)** - service to deploy and manage containers

Containers contain everything needed to run an application

Multiple containers can be used on the same host/instance

Containers do not affect other containers.  Meaning, .NET could be deployed in one container and another version in a different container
neither of these will interfere with the other

Containers provide:
- Increased portibility (can be used locally, on-prem, or cloud).  "If it works on my local computer, it works in the cloud."
- Efficiency for development
- Less overhead - the OSs of each container do not need to be managed as much

## Azure Kubernetes Service (AKS)
**PaaS** model

Created and developed by Google

**Kubernetes (K8s)** is Greek for "Captain"

K8s:
- Open source
- Provides orchestration for containers, makes sure they are configured as needed
- Scales as needed, will create more containers as needed or decrease them
- Can load balance requests to the containers

AKS takes care of the underlying hardware, just need to choose the image to use and the configuration
1. Create an AKS cluster using a specific container from the **Azure Container Registry (ACR)**
2. The cluster creates pods, which has shared networking and storage (basically per AZ)
   - Pods contain onr or more containers
   - Pods are hosted on "nodes" which is the underlying VM/host

ACR - a location to store containers and provide access to the containers

## Windows Virtual Desktop
Provides access to Windows 10 virtually and remotely

Benefits:
- Can reuse Windows 10 licenses - reduces cost
- Concurrency - multiple users canuse the same VM instance concurrently, allowing for better utilization
- Access Anywhere using an internet browser
- Data is secure on the internal network, than residing on a physical computer outside the network
- Integrated with AAD Connect and can use SSO for authentication

## Functions
Should perform a single function

Runs once and stops

Best used for web applications to call the function and the functions returns some data or performs a process

Saves money since the functions only cost while they run

Can scale as needed, more functions will spawn to handle the amount of requests needed