---
title: Azure Synapse connectivity settings
description: An article that teaches you to configure connectivity settings in Azure Synapse Analytics 
ms.service: synapse-analytics 
ms.topic: overview
ms.subservice: security 
ms.date: 12/03/2021 
author: alexshinmsft 
ms.author: seshin 
ms.reviewer: wiassaf
---

# Azure Synapse Analytics connectivity settings

This article will explain connectivity settings in Azure Synapse Analytics and how to configure them where applicable.

## Public network access 

You can use the public network access feature to allow incoming public network connectivity to you Azure Synapse workspace. 

- When public network access is **disabled**, you can connect to your workspace only using [private endpoints](synapse-workspace-managed-private-endpoints.md). 
- When public network access is **enabled**, you can connect to your workspace also from public networks. You can manage this feature both during and after your workspace creation. 

> [!IMPORTANT]
> This feature is only available to Azure Synapse workspaces associated with [Azure Synapse Analytics Managed Virtual Network](synapse-workspace-managed-vnet.md). However, you can still open your Synapse workspaces to the public network regardless of its association with managed VNet. 

Selecting the **Disable** option will not apply any firewall rules that you may configure. Additionally, your firewall rules will appear greyed out in the Network setting in Synapse portal. Your firewall configurations will be reapplied when you enable public network access again. 

> [!TIP]
> When you revert to enable, allow some time before editing the firewall rules.

### Configure public network access when you create your workspace

1.    Select the **Networking** tab when you create your workspace in [Azure portal](https://aka.ms/azureportal).
2.    Under Managed virtual network, select **Enable** to associate your workspace with managed virtual network and permit public network access. 

       :::image type="content" source="./media/connectivity-settings/create-synapse-workspace-managed-virtual-network-1.png" alt-text="Create Synapse workspace, networking tab, Managed virtual network setting" lightbox="media/connectivity-settings/create-synapse-workspace-managed-virtual-network-1.png":::

3. Under **Public network access**, select **Disable** to deny public access to your workspace. Select **Enable** if you want to allow public access to your workspace.

   :::image type="content" source="./media/connectivity-settings/create-synapse-workspace-public-network-access-2.png" alt-text="Create Synapse workspace, networking tab, public network access setting" lightbox="media/connectivity-settings/create-synapse-workspace-public-network-access-2.png"::: 

4.    Complete the rest of the workspace creation flow.

### Configure public network access after you create your workspace

1.    Select your Synapse workspace in [Azure portal](https://aka.ms/azureportal).
2.    Select **Networking** from the left navigation.
3.    Select **Disabled** to deny public access to your workspace. Select **Enabled** if you want to allow public access to your workspace.

       :::image type="content" source="./media/connectivity-settings/synapse-workspace-networking-public-network-access-3.png" alt-text="In an existing Synapse workspace, networking tab, public network access setting is enabled" lightbox="media/connectivity-settings/synapse-workspace-networking-public-network-access-3.png"::: 

4.    When disabled, the **Firewall rules** gray out to indicate that firewall rules are not in effect. Firewall rule configurations will be retained. 

       :::image type="content" source="./media/connectivity-settings/synapse-workspace-networking-firewall-rules-4.png" alt-text="In an existing Synapse workspace, networking tab, public network access setting is disabled, attention to the firewall rules" lightbox="media/connectivity-settings/synapse-workspace-networking-firewall-rules-4.png"::: 
 
5.    Select **Save** to save the change. A notification will confirm that the network setting was successfully saved.

## Connection policy
The connection policy for Synapse SQL in Azure Synapse Analytics is set to *Default*. You cannot change this in Azure Synapse Analytics. You can learn more about how that affects connections to Synapse SQL in Azure Synapse Analytics [here](../../azure-sql/database/connectivity-architecture.md#connection-policy). 

## Minimal TLS version
Synapse SQL in Azure Synapse Analytics allows connections using all TLS versions. You cannot set the minimal TLS version for Synapse SQL in Azure Synapse Analytics.

Starting in December 2021, a requirement for TLS 1.2 has been implemented for new Synapse Workspaces only. Login attempts to the newly created Synapse workspace from connections using a TSL version lower than 1.2 will fail. 


## Next steps

 - Create an [Azure Synapse Workspace](./synapse-workspace-ip-firewall.md).
