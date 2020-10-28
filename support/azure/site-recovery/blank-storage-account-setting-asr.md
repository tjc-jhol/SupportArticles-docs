---
title: Storage account setting is blank in Azure Site Recovery
description: Fixes an issue in which the Storage Account list is blank when you try to configure protection group settings in Azure Site Recovery.
ms.date: 10/10/2020
ms.prod-support-area-path: 
ms.service: backup
ms.author: genli
author: genli
ms.reviewer: markstan
---
# Storage account setting is blank in Azure Site Recovery

_Original product version:_ &nbsp; Azure Backup  
_Original KB number:_ &nbsp; 3093586

## Symptoms

When you try to configure protection group settings in Microsoft Azure Site Recovery (ASR), the **Storage Account** list may be blank. This prevents the wizard from being able to finish.

:::image type="content" source="./media/blank-storage-account-setting-asr/3093587.PNG" alt-text="Specify Protection Group Settings Blank.":::

The setup process is described in the following article: [Set up protection between on-premises VMware virtual machines or physical servers and Azure](/azure/site-recovery/vmware-azure-tutorial).

## Cause

This error may occur if the storage account isn't configured to be geo-redundant. By default, storage accounts are geo-redundant. However, you can manually disable geo-redundancy during account setup.

## Resolution

To fix this issue, follow these steps:

1. Cancel the Create Protection Group wizard.
2. Either create a new storage account or change the replication setting to **geo redundant**. This setting is located in the Azure Portal under the storage account settings properties on the Configure tab.
3. Click Save to commit the change.
4. Restart the Create Protection Group wizard.