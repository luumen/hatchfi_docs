
title: Hatchfi API Authentication
slug: WSpA-hatchfi-api-authentication
createdAt: Mon May 30 2022 06:15:13 GMT+0000 (Coordinated Universal Time)
updatedAt: Sun Aug 07 2022 20:49:43 GMT+0000 (Coordinated Universal Time)
---

## Hatchfi Authentication

Hatchfi authentication allows you to quickly and securely authenticate your application to the Hatchfi backend.&#x20;

Each project will have a unique `API Key` and `Secret Key` generated automatically for you.

We provide you with two methods of authentication: frontend auth and backend auth. With our backend authentication methods, you'll have the choice of authenticating with or without our SDK.



***

## [](https://docs.hatchfi.co/hatchfi-authentication#hatchfi-frontend-authentication)Hatchfi Frontend Authentication

### Requirements

*   **clientId** - represents your application identification (found in your dashboard)

*   **authUrl*** *- URL endpoint to authenticate against

*   **userId*** *- the user UUID you'd like to authenticate

```javascript
// This example requires you to use our Hatchfi JS SDK
const hatchfi = Hatchfi.init({
  clientId: "6fb511c5b5e82cb8d4c14f0ce8504c2fc9b9ed5d34a26822693926de02eab1a3",
  authUrl: "https://api.hatchfi.co/v1/login",
  userId: "bc535daf-98a2-478b-bb5f-614d11aa7a78",
});
```

***

## [](https://docs.hatchfi.co/hatchfi-authentication#hatchfi-backend-authentication)Hatchfi Backend Authentication

### Requirements

*   **clientId*** *- represents your application identification (found in your project dashboard)

*   **apiKey*** *- found in your project dashboard

*   **secretKey*** *- found in your project dashboard

You can then create or authorize the `user` object with the `auth` method.

:::codeblocktabs
```curl
curl --request POST \
    --url https://api.hatchfi.co/v1/auth/login \
    --header 'X-Hatchfi-Api: c1ff770567a34682a23f14a278eed12e' \
    --header 'X-Hatchfi-User-Id: 4e22d4b5-0cef-413f-898e-73c3eb6d4921' \
    --header 'X-Hatchfi-Secret: 5e1fa74024f015322951ab8a3734841a517ed7ed93b0ec1c' \
    --header 'application/json'
```

```javascript
const hatchfi = Hatchfi.init({
  clientId: clientId,
  apiKey: apiKey,
  secretKey: secretKey,
});

let user = hatchfi.auth("unique-identifier-for-your-user");
```
:::

There are two ways to authenticate your users from your frontend with the Hatchfi SDK or without it. Whichever route you chose, you'll need to have your `clientId` and `userId` ready to go.

***

## Without Hatchfi's SDK

In order to authenticate your users with Hatchfi, you'll need to log the user in and generate a session token. You can do set up an endpoint on your server that reaches out to our `/auth/login`[](https://docs.hatchfi.co/hatchfi-authentication#hg-hatchfi-frontend-authentication) endpoint.

```nodejs
const axios = require("axios");

app.post("/auth", async (req, res) => {
  const options = {
    method: "POST",
    url: "https://api.hatchfi.co/v1/auth/login",
    headers: {
      "X-Hatchfi-Api": apiKey,
      "X-Hatchfi-Secret": secretKey,
      "X-Hatchfi-User-Id": req.body.userId,
      "Content-Type": "application/json",
    },
  };

  await axios
    .request(options)
    .then(function (response) {
      res.send(response.data);
    })
    .catch(function (error) {
      console.error(error);
      res.send(error.message);
    });
});

// Returns an Object
// {
//   userId: "your-users-unique-id",
//   token: "token-that-was-generated-for-this-user"
// }
```

***

## With Hatchfi's SDK

When dealing with our SDK, the process is a bit easier; you'll need to import our SDK into your project and fill in the proper fields

*   **clientId*** *- represents your application identification (found in your dashboard)

*   **authUrl*** *- URL endpoint to authenticate against

*   **userId*** *- the user UUID you'd like to authenticate

```javascript
import Hatchfi from "@hatchfi/hatchfi"

// This example requires you to use our Hatchfi JS SDK
const hatchfi = Hatchfi.init({
  clientId: "6fb511c5b5e82cb8d14c14f0ce85104c2fc9b9ed5d234a263822693de02eab1a3",
  authUrl: "https://api.hatchfi.co/v1/login",
  userId: "bc235daf-98a2-478b-b45f-614d31aa7a78",
});
```










