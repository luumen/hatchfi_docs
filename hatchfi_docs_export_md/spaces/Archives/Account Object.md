
title: Account Object
slug: nl0m-account-object
createdAt: Tue May 31 2022 02:46:24 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 06:20:44 GMT+0000 (Coordinated Universal Time)
---

Hatchfi's `Account` object lives within the `User` model and contains important data about each connection.

The core object consists of:

| *Field*        | *Description*                                                   |
| -------------- | --------------------------------------------------------------- |
| *Provider*     | The name of the `Provider`                                      |
| *Balances*     | The `Providers` ticker or symbol                                |
| *Blockchain*   | The blockchain                                                  |
| *Address*      | The address of the connection, if applicable defaults to `null` |
| *ResourceType* | Type of object, always `account`                                |

Below is an example of the `Account` object

```json
{
	"provider": "gemini",
	"balances": [
		{
			"ticker": "USD",
			"providerTicker": "USD",
			"name": "USD",
			"fiatTicker": "USD",
			"fiatValue": null,
			"logo": null,
			"resourceType": null,
			"assetType": null,
			"amount": "0.00233136",
			"decimals": null
		},
		{
			"ticker": "BAT",
			"providerTicker": "BAT",
			"name": "BAT",
			"fiatTicker": "USD",
			"fiatValue": null,
			"logo": null,
			"resourceType": null,
			"assetType": null,
			"amount": "14.537522397447460096",
			"decimals": null
		},
		{
			"ticker": "SPELL",
			"providerTicker": "SPELL",
			"name": "SPELL",
			"fiatTicker": "USD",
			"fiatValue": null,
			"logo": null,
			"resourceType": null,
			"assetType": null,
			"amount": "1978.16234",
			"decimals": null
		}
	],
	"blockchain": "gemini",
	"resourceType": "account",
	"address": "gemini"
	"id": "9edf21cd-0f05-479a-9c47-7e86a60f118d"
}
```

