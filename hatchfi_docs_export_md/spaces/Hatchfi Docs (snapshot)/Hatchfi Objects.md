
title: Hatchfi Objects
slug: tw-YcoQ0Y-r5B9ekN9702
createdAt: Mon May 30 2022 06:46:01 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 06:03:24 GMT+0000 (Coordinated Universal Time)
---

## Overview

This is a list of Hatchfi's API objects that are currently available. Right now, our API supports `accounts`, `transactions`, `providers`, and `balances`.

## Account Object

Here is an example of an account object, to review this object more in-depth please [read more →](https://docs.hatchfi.co/account-object)

```json
    {
	"provider": [
		{
			"inputs": [],
			"notes": null,
			"resourceType": "provider",
			"name": "gemini",
			"displayName": "Gemini",
			"authType": "read_only"
		}
	],
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
	"wallets": [
		{
			"address": "gemini",
			"ticker": "gemini",
			"id": "bc545daf-98a1-478b-bb5f-613d11aa7a78"
		}
	],
	"id": "9edf21cd-0f05-479a-9c47-7e86a60f118d"
}
```

## [](https://docs.hatchfi.co/hatchfi-objects#transaction-object)Transaction Object

Here is an example of a transaction object, to review this object more in-depth please [read more →](https://docs.hatchfi.co/transaction-object)

```json
[
  {
    parts: [
      {
        amount: "0",
        direction: "sent",
        fiatTicker: null,
        fiatValue: null,
        otherParties: ["0x7f268357a8c2552623316e2562d90e642bb538e5"],
        providerTicker: "ETH",
        ticker: "ETH",
        resourceType: "fee",
        _id: "623c1a12650aa0589803d47d",
      },
    ],
    fees: [
      {
        fiatTicker: null,
        fiatValue: null,
        resourceType: "fee",
        type: "network",
        ticker: "eth",
        providerTicker: "eth",
        amount: "4431586",
      },
    ],
    fiatCalculatedAt: null,
    resourceType: "transaction",
    accountId: "a2f736ae-46c0-4b96-8cf6-234e29059141",
    status: "1",
    transactionType: "other",
    initiatedAt: 1648073395,
    confirmedAt: 1648073395,
  },
]
```

## [](https://docs.hatchfi.co/hatchfi-objects#provider-object)Provider Object

Here is an example of a provider object, to review this object more in-depth please [read more →](https://docs.hatchfi.co/provider-object)

```json
{
    scopes: [],
    currencies: [],
    inputs: ["address"],
    notes: null,
    resourceType: "provider",
    name: "solana",
    displayName: "Solana",
    logo: "https://hatchfi.co/providers/solana.png",
    authType: "address",
}
```

## [](https://docs.hatchfi.co/hatchfi-objects#balance-object)Balance Object

Here is an example of a provider object, to review this object more in-depth please [read more →](https://docs.hatchfi.co/balance-object)

```json
{
  "ticker": "SPELL",
  "providerTicker": "SPELL",
  "name": "SPELL",
  "fiatTicker": "USD",
  "fiatValue": null,
  "logo": null,
  "resourceType": "balance",
  "assetType": "ERC-20",
  "amount": "1978.16234",
  "decimals": 18
}
```





