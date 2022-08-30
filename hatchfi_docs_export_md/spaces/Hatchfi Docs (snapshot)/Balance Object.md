
title: Balance Object
slug: M6qQZhHW5s7FCUfsHorEL
createdAt: Tue May 31 2022 02:46:22 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 06:03:24 GMT+0000 (Coordinated Universal Time)
---

Hatchfi's `Balance` object lives within the `Account` model and contains important data about each connection's balance.

The core `Balance` object consists of:

| *Field*          | *Description*                                |
| ---------------- | -------------------------------------------- |
| *Ticker*         | The currency's ticker or symbol              |
| *ProviderTicker* | The `Providers` ticker or symbol             |
| *Name*           | The currencies name                          |
| *FiatTicker*     | The fiat currency's ticker or symbol         |
| *FiatValue*      | The fiat value of the currency               |
| *Logo*           | A URL for the logo of the currency           |
| *ResourceType*   | Type of object, always `balance`             |
| *AssetType*      | The type of asset, depends on the `Provider` |
| *Amount*         | The amount in decimal format                 |
| *Decimals*       | The number of decimals for this currency     |

Below is an example of the `Balance` object

```json
{
  "ticker": "SPELL",
  "providerTicker": "gemini",
  "name": "SPELL",
  "fiatTicker": "USD",
  "fiatValue": "24.983",
  "logo": null,
  "resourceType": "balance",
  "assetType": "ERC-20",
  "amount": "1978.16234",
  "decimals": 18
}
```

###

