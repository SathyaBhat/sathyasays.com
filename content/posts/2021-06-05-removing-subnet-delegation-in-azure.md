---
title: How to Remove Subnet Delegations associated with an Azure Virtual Network(VNET) Subnet
author: Sathyajith Bhat
type: post
date: 2021-06-05
url: /2021/06/05/delete-azure-vnet-subnet-delegation/
featured_image: https://azurecomcdn.azureedge.net/mediahandler/acomblog/media/Default/blog/6a669a37-0ef5-41b3-8ea7-449552243735.png
categories: 
  - DevOps
tags:
  - Azure


---

I was giving Azure Container Instances a try and it seemed to work okay. However, I launched the container in a [VNET](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview) with a subnet that was empty but was supposed to be used for an Azure Cache for Redis deployment. [Buried in the docs](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-virtual-network-concepts), Azure mentions a limitation that containers launched from an Azure Container Instances in a VNET, must be deployed to a subnet that cannot contain other resource types.

> To deploy container groups to a subnet, the subnet can't contain other resource types. Remove all existing resources from an existing subnet prior to deploying container groups to it, or create a new subnet.

So why is this a problem? The subnet was now delegated to be used by Azure Container Instances. Trying to find an empty subnet from a pre-allocated VNET with no overlaps can be quite a challenge, and the subnet was originally dedicated to Azure Cache for Redis, which also needs a dedicated subnet. When I tried to deploy the cache, I got the error message:

> The subnet is delegated to the service(s) : Microsoft.ContainerInstance/containerGroups


I tried to remove the subnet delegation (read more about [subnet delegation](https://docs.microsoft.com/en-us/azure/virtual-network/subnet-delegation-overview)) using the steps mentioned in [the docs](https://docs.microsoft.com/en-us/azure/virtual-network/manage-subnet-delegation#remove-subnet-delegation-from-an-azure-service) but this also failed with another cryptic message about serviceAssociationLinks being present. 

Trying to find details about serviceAssociationLinks lead to a dead end. Finally, I came across this [GitHub issue](https://github.com/MicrosoftDocs/azure-docs/issues/48902#issuecomment-685854862) which explains how you can delete the service association link using the Azure CLI.


```
az rest --method delete --uri https://management.azure.com/subscriptions/<subscription id>/resourceGroups/<resource group>/providers/Microsoft.Network/virtualNetworks/<vnet name>/subnets/<subnet name>/providers/Microsoft.ContainerInstance/serviceAssociationLinks/default?api-version=2018-10-01

```

once the Service association links were deleted, I was able to remove the Subnet delegation using Azure CLI

```
az network vnet subnet update --resource-group <resource group name> --name <subnet name> --vnet-name <vnet name> --remove delegations
```
