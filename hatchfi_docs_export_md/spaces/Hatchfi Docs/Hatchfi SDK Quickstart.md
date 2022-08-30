
title: Hatchfi SDK Quickstart
slug: UJ0S-hatchfi-sdk-quickstart
createdAt: Sun Aug 07 2022 21:01:04 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Aug 16 2022 18:15:50 GMT+0000 (Coordinated Universal Time)
---

If you're using Node.js or a JavaScript framework, the easiest way to connect your application to Hatchfi is through our [Hatchfi JavaScript SDK](https://www.npmjs.com/package/@hatchfi/sdk-js)

***

## Hatchfi SDK for JavaScript

Getting started with the Hatchfi JS SDK is quick and easy. If you need assistance along the way, you can create an [issue](https://github.com/luumen/hatchfi-sdk-js/issues/new), join our [discord](https://discord.gg/hatchfi), or reach out to us at our [support email](mailto\:contact@hatchfi.co).

## Getting Started

You can visit the entire repo here: <https://github.com/luumen/hatchfi-sdk-js>

### Installation&#x20;

Install the SDK into your project with NPM

```shell
npm i @hatchfi/sdk-js
```

### Initialization and Authentication

Once installed, we'll import and then initialize it.

:::codeblocktabs
```nodejs
const Hatchfi = require("@hatchfi/sdk-js");

// Initalize the SDK with your clientId, API Key, and your Secret Key.
const hatchfi = Hatchfi.init({
  clientId: clientId,
  apiKey: apiKey,
  secretKey: secretKey,
});

// Authenticate your selected user with their UID.
let user = hatchfi.auth("unique-identifier-for-your-user");
```

```javascript
import Hatchfi from "@hatchfi/sdk-js";

// Initalize the SDK with your clientId, Auth URL, and your users UID.
const hatchfi = Hatchfi.init({
  clientId: "6fb511c5b5e82cb8d4c14f0ce8504c2fc9b9ed5d34a26822693926de02eab1a3",
  authUrl: "https://api.hatchfi.co/v1/login",
  userId: "bc535daf-98a2-478b-bb5f-614d11aa7a78",
});
```
:::

The `hatchfi` object now gives you access to the Hatchfi API and the ability to authenticate a user. You'll need to authenticate a user, you'll need to call `.auth(userId)` from the `hatchfi` object.

## Making Requests

We're ready to start making calls now that the `hatchfi` object is initialized. We'll cover all of our available endpoints, which can be found in our [Hatchfi API: Endpoints](https://docs.hatchfi.co/hatchfi-api-endpoints) section.

### All Accounts

This function returns all of the specified user's accounts. [Read more →](https://docs.hatchfi.co/hatchfi-api-endpoints#DrJZn)

```javascript
const accounts = await user.accounts.getAll();
```

### Specific Account

This function returns the specified account of the selected user. [Read more →](https://docs.hatchfi.co/hatchfi-api-endpoints#1fmfv)

```javascript
const account = await user.accounts.getOne(accountId);
```

### Delete All Accounts

This function removes all of the accounts and transactions of the selected user. `DeleteAll()` comes in handy when users request to remove all of their connections from your platform and the Hatchfi database. [Read more →](https://docs.hatchfi.co/hatchfi-api-endpoints#lwd-t)

```javascript
await user.accounts.deleteAll();
```

### Delete Specific Account

This function removes the specified account and related transactions from the selected user. `deleteOne()` comes in handy when a user wants to remove a single connection from your platform and the Hatchfi database. [Read more →](https://docs.hatchfi.co/hatchfi-api-endpoints#lwd-t)

```javascript
await user.accounts.deleteOne(accountId);
```

### Get All Transactions

This function returns all of the selected account's transactions. [Read more →](https://docs.hatchfi.co/hatchfi-api-endpoints#oCfZV)

```javascript
const transactions = await user.transactions.getAll();
```

### ﻿[﻿](https://docs.hatchfi.co/hatchfi-actions#specific-transaction)Get Specific Transaction Endpoint[](https://docs.hatchfi.co/hatchfi-api-endpoints#YF8cc)

This function returns the specified transaction of the selected user based on the transaction's id.&#x20;

[Read more →](https://docs.hatchfi.co/hatchfi-api-endpoints#YF8cc)

```javascript
const transaction = await user.transactions.getOne(transactionId);
```

