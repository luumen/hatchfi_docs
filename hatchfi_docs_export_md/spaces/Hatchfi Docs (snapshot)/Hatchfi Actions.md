
title: Hatchfi Actions
slug: 3MX3nLAMH4SS8WjNv83X8
createdAt: Mon May 30 2022 03:02:25 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Aug 09 2022 05:38:51 GMT+0000 (Coordinated Universal Time)
---

Hatchfi Actions are all of our read endpoints that you can use to fetch data, these include:

*   Accounts

*   Balances

*   Transactions

Hatchfi actions come easily accessible with our [Hatchfi JS SDK](todo\:linktonpm) or through a headless setup, where you can hit our endpoints in whatever way works best for your setup. These are all authenticated endpoints and require a `clientId`, `apiKey`, and `secretKey` with each call to ensure the safety of your data.

## [](https://docs.hatchfi.co/hatchfi-actions#all-accounts)All Accounts

This function returns all of the specified user's accounts.

:::codeblocktabs
```curl
 curl --request GET \
    --url https://api.hatchfi.co/v1/accounts/ \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

```python
import requests;

url = 'https://api.hatchfi.co/v1/accounts/'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("GET", url, data=payload, headers=headers)
print(response.text);
```

```javascript
const accounts = await hatchfi.accounts.getAll();
```
:::

The `getAll()` function will return an array of all the specified user's `Account` objects. If you are using our SDK, Hatchfi automatically knows who the "authenticated" user is so the method will be called without any arguments. If you are *not* using our SDK, you can query all accounts by inserting the header `x-hatchfi-user-id`. This will allow you, the project owner, to query all of your users' accounts within your application.

```json
[
  {
		"provider": [
			{
				"inputs": [],
				"notes": null,
				"resourceType": "provider",
				"id": "62284a5e7f596a3b09e8a5da",
				"name": "bsc",
				"displayName": "Binance Smart Chain",
				"authType": "read_only"
			}
		],
		"balances": [
			{
				"ticker": "BNB",
				"providerTicker": "BNB",
				"name": "Binance Coin",
				"fiat_ticker": "USD",
				"misc": [],
				"id": "62284a5e7f596a3b09e8a5db",
				"assetType": "BEP20",
				"amount": "495997767937420876",
				"decimals": 8
			}
		],
		"blockchain": "bsc",
		"resourceType": "account",
		"wallets": [
			{
				"address": "0xfb216f3F67065d9274d04a057fBC837f4226c864",
				"ticker": "BNB",
				"id": "4e52d3b5-0eef-443f-898e-73c35b6d4951"
			}
		],
		"id": "a5fba948-71de-41a4-b2b7-1a2d291b76c1"
	},
  ...
]
```

## [](https://docs.hatchfi.co/hatchfi-actions#specfic-account)Specific Account

This function returns the specified account of the selected user.

:::codeblocktabs
```curl
import requests;

url = 'https://api.hatchfi.co/v1/accounts/:accountId'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("GET", url, data=payload, headers=headers)
print(response.text);
```

```python
import requests;

url = 'https://api.hatchfi.co/v1/accounts/:accountId'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("GET", url, data=payload, headers=headers)
print(response.text);
```

```javascript
const accounts = await hatchfi.accounts.getOne(accountId);
```
:::

The `getOne()` function will return an `Account` object, like in the example below:

```json
{
  "provider": [
    {
      "inputs": [],
      "notes": null,
      "resourceType": "provider",
      "id": "62284a5e7f596a3b09e8a5da",
      "name": "bsc",
      "displayName": "Binance Smart Chain",
      "authType": "read_only"
    }
  ],
  "balances": [
    {
      "ticker": "BNB",
      "providerTicker": "BNB",
      "name": "Binance Coin",
      "fiat_ticker": "USD",
      "misc": [],
      "id": "62284a5e7f596a3b09e8a5db",
      "assetType": "BEP20",
      "amount": "495997767937420876",
      "decimals": 8
    }
  ],
  "blockchain": "bsc",
  "resourceType": "account",
  "wallets": [
    {
      "address": "0xfb216f3F67065d9274d04a057fBC837f4226c864",
      "ticker": "BNB",
      "id": "4e52d3b5-0eef-443f-898e-73c35b6d4951"
    }
  ],
  "id": "a5fba948-71de-41a4-b2b7-1a2d291b76c1"
}
```

## [](https://docs.hatchfi.co/hatchfi-actions#delete-all-accounts)Delete All Accounts

This function removes all of the accounts the selected user. deleteAll() comes in handy when a user requests to remove all of their connections from your platform and the Hatchfi database.

:::codeblocktabs
```curl
 curl --request DELETE \
    --url https://api.hatchfi.co/v1/accounts/delete \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

```python
import requests;

url = 'https://api.hatchfi.co/v1/accounts/delete'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("DELETE", url, data=payload, headers=headers)
print(response.text);
```

```javascript
await hatchfi.accounts.deleteAll();
```
:::

## [](https://docs.hatchfi.co/hatchfi-actions#delete-specfic-account)Delete Specfic Account

This function removes the specified account from the selected user. deleteOne() comes in handy when a user wants to remove a single connection from your platform and the Hatchfi database.

:::codeblocktabs
```curl
curl --request DELETE \
    --url https://api.hatchfi.co/v1/accounts/:accountId \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

```python
import requests;

url = 'https://api.hatchfi.co/v1/accounts/:accountId'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("DELETE", url, data=payload, headers=headers)
print(response.text);
```

```javascript
await hatchfi.accounts.deleteOne(accountId);
```
:::

## [](https://docs.hatchfi.co/hatchfi-actions#all-transactions)All Transactions

This function returns all of the selected account's transactions.

:::codeblocktabs
```curl
curl --request GET \
    --url https://api.hatchfi.co/v1/accounts/:accountId/transactions \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

```python
import requests;

url = 'https://api.hatchfi.co/v1/accounts/:accountId/transactions'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("GET", url, data=payload, headers=headers)
print(response.text);
```

```javascript
const transactions = await hatchfi.transactions.getAll(accountId);
```
:::

The `getAll()` function will return an array of `Transaction` objects, like in the example below:

```javascript
[
  {
    "parts": [
      {
        "direction": "sent",
        "ticker": "ETH",
        "providerTicker": "ETH",
        "amount": "0",
        "fiat_value": null, // coming soon
        "otherParties": [
          "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2"
        ],
        "resourceType": "part",
        "id": "621bdfd1ab834d12b48fa02e"
      }
    ],
    "fees": [
      {
        "asset_is_verified": false,
        "fiat_value": null, // coming soon
        "id": "621bdfd1ab834d12b48fa02f",
        "type": "network",
        "ticker": "eth",
        "providerTicker": "eth",
        "amount": "7152665"
      }
    ],
    "id": "621bdfd1ab834d12b48fa030",
    "txId": "0x9b6d9c82cc58f374516924d186fba56ad0bafe880e1bc474ee2a0c3183c62507",
    "accountId": "a2f736ae-46c0-4b96-8cf6-234e29059141",
    "local_id": "0001", // selected users unique identifier
    "status": "1",
    "transactionType": "other",
    "initiatedAt": 1645993835,
    "confirmedAt": 1645993835
  },
  ...
]
```

## [](https://docs.hatchfi.co/hatchfi-actions#specific-transaction)Specific Transaction

This function returns the specified transaction of the selected user based on the transaction's id.

:::codeblocktabs
```curl
curl --request GET \
    --url https://api.hatchfi.co/v1/accounts/:accountId/transactions/:transactionId \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

```python
import requests;

url = 'https://api.hatchfi.co/v1/accounts/:accountId/transactions/:transactionId'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("GET", url, data=payload, headers=headers)
print(response.text);
```

```javascript
const transaction = await hatchfi.transactions.getOne(transactionId);
```
:::

The `getOne()` function will return a `Transaction` object, like in the example below:

```javascript
{
  "parts": [
    {
      "direction": "sent",
      "ticker": "ETH",
      "providerTicker": "ETH",
      "amount": "0",
      "fiat_value": null, // coming soon
      "otherParties": ["0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2"],
      "resourceType": "part",
      "id": "621bdfd1ab834d12b48fa02e"
    }
  ],
  "fees": [
    {
      "asset_is_verified": false,
      "fiat_value": null, // coming soon
      "id": "621bdfd1ab834d12b48fa02f",
      "type": "network",
      "ticker": "eth",
      "providerTicker": "eth",
      "amount": "7152665"
    }
  ],
  "id": "621bdfd1ab834d12b48fa030",
  "txId": "0x9b6d9c82cc58f374516924d186fba56ad0bafe880e1bc474ee2a0c3183c62507",
  "accountId": "a2f736ae-46c0-4b96-8cf6-234e29059141",
  "userId": "0001", // selected users unique identifier
  "status": "1",
  "transactionType": "other",
  "initiatedAt": 1645993835,
  "confirmedAt": 1645993835
}
```

## [](https://docs.hatchfi.co/hatchfi-actions#balance-history)Balance History

This function returns the current user's balance history.

:::hint
ℹ️ Balance history starts from the day the account connection is made.
:::

:::codeblocktabs
```curl
curl --request GET \
    --url https://api.hatchfi.co/v1/history \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

```python
import requests;

url = 'https://api.hatchfi.co/v1/history'

payload = ""
headers = {
    "X-Hatchfi-Api": '<API-KEY>',
    "X-Hatchfi-Secret": "<SECRET-KEY>",
    "X-Hatchfi-User-Id": "<USER-ID",
}

response = requests.request("GET", url, data=payload, headers=headers)
print(response.text);
```

```javascript
const transaction = await hatchfi.history.getHistory();
```
:::

The `getHistory()` method will return an array of accounts with balances attached, like in the example below:

```javascript
[
	{
		"accounts": [
			{
				"provider": "ethereum",
				"balances": [
					{
						"ticker": "ETH",
						"providerTicker": "ETH",
						"name": "Ethereum",
						"fiatTicker": "USD",
						"fiatValue": "14.37",
						"logo": null,
						"resourceType": null,
						"misc": [],
						"_id": "62602de7535f996bd09a0027",
						"assetType": "ERC20",
						"amount": "4682413698650305",
						"decimals": 18
					}
				],
				"blockchain": "ethereum",
				"resourceType": "account",
				"address": "0x87c12cf321ea93742ff8075cf0b22021b2d264f9",
				"ticker": "ETH",
				"_id": "62602de7535f996bd09a0028",
				"id": "9de41a9b-1161-4b34-ba33-65e9e7edeffa"
			},
		],
		"date": "4/28/2022"
	},
  ...
]
```

***

:::hint
📣 Do you need an endpoint that we don't have? Suggest it on our [Roadmap](https://feedback.hatchfi.co)
:::

