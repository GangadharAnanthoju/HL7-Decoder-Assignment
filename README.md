# HL7-Decoder-Assignment

## Prerequisites

- An Azure Integration Account is required.
- Upload the HL7 v2.5 schemas to the Integration Account before running this project.
- Confirm `ADT_A01` for v2.5 is uploaded, typically with:
	- `ADT_A01_25_GLO_DEF.xsd`
	- `segments_25.xsd`
	- `datatypes_25.xsd`
	- `tablevalues_25.xsd`

## Local setup

1. Open the project folder in VS Code:
	 - `c:\Data2\HL7-Decoder-Assignment\HL7-Decoder-Assignment`
2. Open this workspace folder:
	 - `la-hl7-decoder-assignment`
3. In `la-hl7-decoder-assignment`, create a file named `local.settings.json`.
4. Paste the following settings into `local.settings.json` and update information from Azure Subscritpion including "WORKFLOW_INTEGRATION_ACCOUNT_CALLBACK_URL

```json
{
	"IsEncrypted": false,
	"Values": {
		"APP_KIND": "workflowapp",
		"ProjectDirectoryPath": "c:\\XXX..\\HL7-Decoder-Assignment\\HL7-Decoder-Assignment",
		"FUNCTIONS_WORKER_RUNTIME": "dotnet",
		"AzureWebJobsStorage": "UseDevelopmentStorage=true",
		"FUNCTIONS_INPROC_NET8_ENABLED": "1",
		"WORKFLOWS_TENANT_ID": "<YOUR_TENANT_ID>",
		"WORKFLOWS_SUBSCRIPTION_ID": "<YOUR_SUBSCRIPTION_ID>",
		"WORKFLOWS_RESOURCE_GROUP_NAME": "<YOUR_RESOURCE_GROUP_NAME>",
		"WORKFLOWS_LOCATION_NAME": "eastus",
		"WORKFLOWS_MANAGEMENT_BASE_URI": "https://management.azure.com/",
		"WORKFLOWS_AUTHENTICATION_METHOD": "managedServiceIdentity",
		"WORKFLOW_INTEGRATION_ACCOUNT_CALLBACK_URL": "<YOUR_INTEGRATION_ACCOUNT_CALLBACK_URL>"
	}
}
```

## Notes

- Replace values specific to your subscription before running locally.
- Keep `local.settings.json` local and do not commit secrets.
