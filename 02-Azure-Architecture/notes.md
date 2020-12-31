# Azure Architecture
## Regions and Availability Zones
Regions are a set of datacenters in a larger geographic location

Pricing can change between regions

Some features are not avaiable in certain regions

Each region is paired with another region.  For example, East US is paired with West US  
  If a region fails, you can failover to another region (need to choose additional regions when created new resources)

# Availability Zones (AZs)
AZs are the datacenters contained in a region (at least 3 AZs in a region)

There are multiple AZs per region

Has their own powers, cooling and network

# Resource Groups
All resources need to be in a resource group

Resource groups are just a logical container
Best to plance similar resources based on a project, for example

Resource groups can contain resources from multiple regions

Can specify permissions to resource groups

# Azure Resource Manager (ARM)
Handles all the creation/updating/deleting of resources in Azure

Can create an ARM template, which is similar to CloudFormation from AWS