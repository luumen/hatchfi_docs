
title: Provider Object 
slug: sm7sv0Lys906mnBm68mF1
createdAt: Tue May 31 2022 02:46:22 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 06:03:24 GMT+0000 (Coordinated Universal Time)
---

Hatchfi's `Provider` contains important metadata about each provider Hatchfi offers.

The core object consists of:

| *Field*        | *Description*                                                                                                  |
| -------------- | -------------------------------------------------------------------------------------------------------------- |
| *Scopes*       | The `Provider's` scope of access                                                                               |
| *Currencies*   | An array of currencies the `Provider` may contain                                                              |
| *Inputs*       | An array of inputs that the `Provider` will need                                                               |
| *Notes*        | Notes for the end-user on [Hatchfi Link](https://docs.hatchfi.co/hatchfi-link)                                 |
| *ResourceType* | Type of object, always `provider`&#x20;                                                                        |
| *Name*         | A lowercase and no spaces format of the `Provider`&#x20;                                                       |
| *DisplayName*  | The name of the `Provider` for user display                                                                    |
| *Logo*         | The link to the `Provider` logo                                                                                |
| *AuthType*     | Type of auth that the `Provider` requires, there are three types: `address` , `token` , and `passPhrase`&#x20; |

Below is an example of the `Balance` object

```json
{
	"scopes": [
		{
			"name": "read_balances",
			"displayName": "Read Balances",
			"description": "Can read all balance information."
		}
	],
	"currencies": null,
	"inputs": [
		"apiKey",
		"secretKey"
	],
	"notes": "Please enter your API and Secret Key.",
	"resourceType": "provider",
	"name": "gemini",
	"displayName": "Gemini",
	"logo": "https://hatchfi.co/providers/gemini.png",
	"authType": "token"
}
```

###

