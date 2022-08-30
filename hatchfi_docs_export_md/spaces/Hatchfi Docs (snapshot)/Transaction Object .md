
title: Transaction Object 
slug: XF-ridgdSzuEbOftoe_EC
createdAt: Tue May 31 2022 02:46:22 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 06:03:24 GMT+0000 (Coordinated Universal Time)
---

Hatchfi's `Transaction` contains important data about each connection's transaction.

The core object consists of:

| *Field*           | *Description*                                                                     |
| ----------------- | --------------------------------------------------------------------------------- |
| *Parts*           | The currency's ticker or symbol                                                   |
| *Fees*            | The `Providers` ticker or symbol                                                  |
| *AccountId*       | The id of the `Account` who owns this `Transaction`                               |
| *Status*          | This indicates the status of the transaction, whether it was a success or failure |
| *TransactionType* | The type of `Transaction` defaults to `other`                                     |
| *ResourceType*    | Type of object, always `transaction`                                              |
| *InitiatedAt*     | A timestamp of when the `Transaction `was initiated                               |
| *ConfirmedAt*     | A timestamp of when the `Transaction `was confirmed by the blockchain             |

Below is an example of the `Transaction` object

```json
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
    resourceType: "transaction",
    accountId: "a2f736ae-46c0-4b96-8cf6-234e29059141",
    status: "1",
    transactionType: "other",
    initiatedAt: 1648073395,
    confirmedAt: 1648073395,
  }
```

###

