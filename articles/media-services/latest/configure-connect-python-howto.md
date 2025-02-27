---
title: Connect to Azure Media Services v3 API - Python
description: This article demonstrates how to connect to Media Services v3 API with Python.
services: media-services
documentationcenter: ''
author: IngridAtMicrosoft
manager: femila
editor: ''

ms.service: media-services
ms.workload: media
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: how-to
ms.date: 11/18/2020
ms.author: inhenkel
ms.custom: devx-track-python

---
# Connect to Media Services v3 API - Python

[!INCLUDE [media services api v3 logo](./includes/v3-hr.md)]

This article shows you how to connect to the Azure Media Services v3 Python SDK using the service principal sign in method.

## Prerequisites

- Download Python from [python.org](https://www.python.org/downloads/)
- Make sure to set the `PATH` environment variable
- [Create a Media Services account](./account-create-how-to.md). Be sure to remember the resource group name and the Media Services account name.
- Follow the steps in the [Access APIs](./access-api-howto.md) topic, selecting the Service principal authentication method. Record the subscription ID, application client ID, the authentication key, and the tenant ID that you need in the later steps.

> [!IMPORTANT]
> Review [naming conventions](media-services-apis-overview.md#naming-conventions).

## Install the modules

To work with Azure Media Services using Python, you need to install these modules.

* The `azure-identity` module, which includes Azure modules for Active Directory.
* The `azure-mgmt-media` module, which includes the Media Services entities.

    Make sure to get [the latest version of the Media Services SDK for Python](https://pypi.org/project/azure-mgmt-media/).

Open a command-line tool and use the following commands to install the modules.

```cmd
pip3 install azure-identity
pip3 install azure-mgmt-media
```

## Connect to the Python client

1. Create a file with a `.py` extension
1. Open the file in your favorite editor
1. Add the the following code to the file. The code imports the required modules and creates the Active Directory credentials object you need to connect to Media Services.

      Set the variables' values to the values you got from [Access APIs](./access-api-howto.md). Update the `ACCOUNT_NAME` and `RESOURCE_GROUP_NAME` variables to the Media Services account name and Resource Group names used when creating those resources.

    ```python
    from azure.identity import ClientSecretCredential 
    from azure.mgmt.media import AzureMediaServices
    
    # Tenant ID for your Azure Subscription
    TENANT_ID = "(update-this-value)"

    # Your Application Client ID of your Service Principal
    CLIENT_ID = "(update-this-value)"

    # Your Service Principal secret key
    CLIENT_SECRET = "(update-this-value)"

    # Your Azure Subscription ID
    SUBSCRIPTION_ID = "(update-this-value)"

    # Your Resource Group name
    RESOURCE_GROUP_NAME = "(update-this-value)"
    
    # Your Azure Media Service account name
    ACCOUNT_NAME = "(update-this-value)"

    credentials = ClientSecretCredential(TENANT_ID, CLIENT_ID, CLIENT_SECRET)
    
    # The Azure Media Services Client
    client = AzureMediaServices(credentials, SUBSCRIPTION_ID)
    
    # Now that you are authenticated, you can manipulate the entities.
    # For example, list assets in your Media Services account
    assets = client.assets.list(RESOURCE_GROUP_NAME, ACCOUNT_NAME)
    
    for i, r in enumerate(assets):
        print(r)
    ```

1. Run the file


## Additional samples

Additional samples are available in GitHub in the [Azure Media Services v3 Python Samples](https://github.com/Azure-Samples/media-services-v3-python) repo.

## Next steps

- Use [Python SDK](https://aka.ms/ams-v3-python-sdk).
- Review the Media Services [Python ref](/python/api/overview/azure/mediaservices/management) documentation.
