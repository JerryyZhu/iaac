# Commands

## Install Azure CLI + Biceps

```
az login
```

```
`az account set --subscription "Concierge Subscription"`
```

```bash
az account list \
   --refresh \
   --query "[?contains(name, 'Concierge Subscription')].id" \
   --output table
```

```
az account set --subscription {your subscription ID}
```

## Output
```json
[
  {
    "cloudName": "AzureCloud",
    "homeTenantId": "",
    "id": "9363ae6f-769e-4d0c-8ad8-f6d3bfed6578",
    "isDefault": true,
    "managedByTenants": [],
    "name": "Pay-As-You-Go",
    "state": "Enabled",
    "tenantId": "",
    "user": {
      "name": "@hotmail.com",
      "type": "user"
    }
  },
  {
    "cloudName": "AzureCloud",
    "homeTenantId": "",
    "id": "e199363b-82d0-4b31-903d-e32280f66e03",
    "isDefault": false,
    "managedByTenants": [],
    "name": "Concierge Subscription",
    "state": "Enabled",
    "tenantId": "",
    "user": {
      "name": "@hotmail.com",
      "type": "user"
    }
  }
]
```


```json
{
  "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Resources/deployments/main",
  "location": null,
  "name": "main",
  "properties": {
    "correlationId": "b6abe8a7-e404-4af6-ba83-67d1bc7a85bf",
    "debugSetting": null,
    "dependencies": [],
    "duration": "PT41.9520051S",
    "error": null,
    "mode": "Incremental",
    "onErrorDeployment": null,
    "outputResources": [
      {
        "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Storage/storageAccounts/toylaunchstoragee199363b",
        "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89"
      }
    ],
    "outputs": null,
    "parameters": null,
    "parametersLink": null,
    "providers": [
      {
        "id": null,
        "namespace": "Microsoft.Storage",
        "providerAuthorizationConsentState": null,
        "registrationPolicy": null,
        "registrationState": null,
        "resourceTypes": [
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "australiaeast"
            ],
            "properties": null,
            "resourceType": "storageAccounts"
          }
        ]
      }
    ],
    "provisioningState": "Succeeded",
    "templateHash": "15438120448063229375",
    "templateLink": null,
    "timestamp": "2021-11-03T01:10:52.639509+00:00",
    "validatedResources": null
  },
  "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89",
  "tags": null,
  "type": "Microsoft.Resources/deployments"
}
```

```json
{
  "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Resources/deployments/main",
  "location": null,
  "name": "main",
  "properties": {
    "correlationId": "1f517d92-6e6c-4d68-901e-32ee3ad3bffa",
    "debugSetting": null,
    "dependencies": [
      {
        "dependsOn": [
          {
            "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Web/serverfarms/toy-product-launch-plan",
            "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89",
            "resourceName": "toy-product-launch-plan",
            "resourceType": "Microsoft.Web/serverfarms"
          }
        ],
        "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Web/sites/toylaunchczyhqbg7si6ce",
        "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89",
        "resourceName": "toylaunchczyhqbg7si6ce",
        "resourceType": "Microsoft.Web/sites"
      }
    ],
    "duration": "PT43.2006632S",
    "error": null,
    "mode": "Incremental",
    "onErrorDeployment": null,
    "outputResources": [
      {
        "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Storage/storageAccounts/toylaunchczyhqbg7si6ce",
        "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89"
      },
      {
        "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Web/serverfarms/toy-product-launch-plan",
        "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89"
      },
      {
        "id": "/subscriptions/e199363b-82d0-4b31-903d-e32280f66e03/resourceGroups/learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89/providers/Microsoft.Web/sites/toylaunchczyhqbg7si6ce",
        "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89"
      }
    ],
    "outputs": null,
    "parameters": {
      "appServiceAppName": {
        "type": "String",
        "value": "toylaunchczyhqbg7si6ce"
      },
      "environmentType": {
        "type": "String",
        "value": "nonprod"
      },
      "location": {
        "type": "String",
        "value": "australiaeast"
      },
      "storageAccountName": {
        "type": "String",
        "value": "toylaunchczyhqbg7si6ce"
      }
    },
    "parametersLink": null,
    "providers": [
      {
        "id": null,
        "namespace": "Microsoft.Storage",
        "providerAuthorizationConsentState": null,
        "registrationPolicy": null,
        "registrationState": null,
        "resourceTypes": [
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "australiaeast"
            ],
            "properties": null,
            "resourceType": "storageAccounts"
          }
        ]
      },
      {
        "id": null,
        "namespace": "Microsoft.Web",
        "providerAuthorizationConsentState": null,
        "registrationPolicy": null,
        "registrationState": null,
        "resourceTypes": [
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "australiaeast"
            ],
            "properties": null,
            "resourceType": "serverfarms"
          },
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "australiaeast"
            ],
            "properties": null,
            "resourceType": "sites"
          }
        ]
      }
    ],
    "provisioningState": "Succeeded",
    "templateHash": "1597058497409060549",
    "templateLink": null,
    "timestamp": "2021-11-03T02:32:41.417639+00:00",
    "validatedResources": null
  },
  "resourceGroup": "learn-3aafa760-06d8-4f16-b7a7-bfc684b95c89",
  "tags": null,
  "type": "Microsoft.Resources/deployments"
}
```