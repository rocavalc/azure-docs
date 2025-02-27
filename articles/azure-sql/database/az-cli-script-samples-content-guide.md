---
title: Azure CLI samples for Azure SQL Database & Managed Instances | Microsoft Docs
titleSuffix: Azure SQL Database & SQL Managed Instance 
description: Find Azure CLI script samples to create and manage Azure SQL Database and Azure SQL Managed Instance.
services: sql-database
ms.service: sql-db-mi
ms.subservice: deployment-configuration
ms.custom: overview-samples, mvc, sqldbrb=2, devx-track-azurecli, seo-azure-cli
ms.devlang: azurecli
ms.topic: sample
author: LitKnd
ms.author: kendralittle
ms.reviewer: mathoma
ms.date: 09/17/2021
keywords: sql database, managed instance, azure cli samples, azure cli examples, azure cli code samples, azure cli script examples
---

# Azure CLI samples for Azure SQL Database and SQL Managed Instance
 
[!INCLUDE[appliesto-sqldb-sqlmi](../includes/appliesto-sqldb-sqlmi.md)]

You can configure Azure SQL Database and SQL Managed Instance by using the <a href="/cli/azure">Azure CLI</a>.

[!INCLUDE [quickstarts-free-trial-note](../../../includes/quickstarts-free-trial-note.md)]

[!INCLUDE [azure-cli-prepare-your-environment.md](../../../includes/azure-cli-prepare-your-environment.md)]

 - This tutorial requires version 2.0 or later of the Azure CLI. If using Azure Cloud Shell, the latest version is already installed.

# [Azure SQL Database](#tab/single-database)

The following table includes links to Azure CLI script examples to manage single and pooled databases in Azure SQL Database. 

|Area|Description|
|---|---|
|**Create databases in Azure SQL Database**||
| [Create a single database and configure a firewall rule](scripts/create-and-configure-database-cli.md) | Creates an SQL Database and configures a server-level firewall rule. |
| [Create elastic pools and move pooled databases](scripts/move-database-between-elastic-pools-cli.md) | Creates elastic pools, moves pooled databases, and changes compute sizes. |
|**Scale databases in Azure SQL Database**||
| [Scale a single database](scripts/monitor-and-scale-database-cli.md) | Scales a database in SQL Database to a different compute size after querying the size information for the database. |
| [Scale an elastic pool](scripts/scale-pool-cli.md) | Scales a SQL elastic pool to a different compute size. |
|**Configure geo-replication and failover**||
| [Add a single database to a failover group](scripts/add-database-to-failover-group-cli.md)| Creates a database and a failover group, adds the database to the failover group, then tests failover to the secondary server. |
| [Configure a failover group for an elastic pool](../../sql-database/scripts/sql-database-add-elastic-pool-to-failover-group-cli.md) | Creates a database, adds it to an elastic pool, adds the elastic pool to the failover group, then tests failover to the secondary server. |
| [Configure and fail over a single database by using active geo-replication](../../sql-database/scripts/sql-database-setup-geodr-and-failover-database-cli.md)| Configures active geo-replication for a database in Azure SQL Database and fails it over to the secondary replica. |
| [Configure and fail over a pooled database by using active geo-replication](../../sql-database/scripts/sql-database-setup-geodr-and-failover-pool-cli.md)| Configures active geo-replication for a database in an elastic pool, then fails it over to the secondary replica. |
| **Auditing and threat detection** |
| [Configure auditing and threat-detection](../../sql-database/scripts/sql-database-auditing-and-threat-detection-cli.md)| Configures auditing and threat detection policies for a database in Azure SQL Database. |
| **Back up, restore, copy, and import a database**||
| [Back up a database](../../sql-database/scripts/sql-database-backup-database-cli.md)| Backs up a database in SQL Database to an Azure storage backup. |
| [Restore a database](../../sql-database/scripts/sql-database-restore-database-cli.md)| Restores a database in SQL Database from a geo-redundant backup and restores a deleted database to the latest backup. |
| [Copy a database to a new server](../../sql-database/scripts/sql-database-copy-database-to-new-server-cli.md) | Creates a copy of an existing database in SQL Database in a new server. |
| [Import a database from a BACPAC file](../../sql-database/scripts/sql-database-import-from-bacpac-cli.md)| Imports a database to SQL Database from a BACPAC file. |
|||

Learn more about the [single-database Azure CLI API](single-database-manage.md#the-azure-cli).

# [Azure SQL Managed Instance](#tab/managed-instance)

The following table includes links to Azure CLI script examples for Azure SQL Managed Instance.

|Area|Description|
|---|---|
| **Create a SQL Managed Instance**||
| [Create a SQL Managed Instance](../../sql-database/scripts/sql-database-create-configure-managed-instance-cli.md)| Creates a SQL Managed Instance. |
| **Configure Transparent Data Encryption (TDE)**||
| [Manage Transparent Data Encryption in a SQL Managed Instance by using Azure Key Vault](../../sql-database/scripts/transparent-data-encryption-byok-sql-managed-instance-cli.md)| Configures Transparent Data Encryption (TDE) in SQL Managed Instance by using Azure Key Vault with various key scenarios. |
|**Configure a failover group**||
| [Configure a failover group for SQL Managed Instance](../../sql-database/scripts/sql-database-add-managed-instance-to-failover-group-cli.md) | Creates two instances of SQL Managed Instance, adds them to a failover group, and then tests failover from the primary SQL Managed Instance to the secondary SQL Managed Instance. |
|||

For additional SQL Managed Instance examples, see the [create](/archive/blogs/sqlserverstorageengine/create-azure-sql-managed-instance-using-azure-cli), [update](/archive/blogs/sqlserverstorageengine/modify-azure-sql-database-managed-instance-using-azure-cli), [move a database](/archive/blogs/sqlserverstorageengine/cross-instance-point-in-time-restore-in-azure-sql-database-managed-instance), and [working with](https://medium.com/azure-sqldb-managed-instance/working-with-sql-managed-instance-using-azure-cli-611795fe0b44) scripts.

Learn more about the [SQL Managed Instance Azure CLI API](../managed-instance/api-references-create-manage-instance.md#azure-cli-create-and-configure-managed-instances).

---