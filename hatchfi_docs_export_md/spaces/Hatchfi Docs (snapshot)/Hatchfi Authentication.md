
title: Hatchfi Authentication
slug: 6zgsibZRtHcyv7y8YGx0Q
createdAt: Mon May 30 2022 06:15:13 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue Aug 09 2022 05:41:33 GMT+0000 (Coordinated Universal Time)
---

## Hatchfi Authentication

Hatchfi authentication allows you, the awesome developer, to securely and safely authenticate your application to the Hatchfi backend. When you create an account, you'll be taken to your Hatchfi Dashboard, where you can generate your first project.

Each project will have a unique `API Key` and `Secret Key` generated automatically for you.

We provide you with two methods of authentication: frontend auth, and backend auth. With our backend authentication methods, you'll have the choice of authenticating with or without our SDK.

## [](https://docs.hatchfi.co/hatchfi-authentication#hatchfi-frontend-authentication)Hatchfi Frontend Authentication

Requirements

*   *clientId* - represents your application identification (found in your dashboard)

*   *authUrl *- URL endpoint to authenticate against

*   *userId *- the user UUID you'd like to authenticate

```javascript
// This example requires you to use our Hatchfi JS SDK
const hatchfi = Hatchfi.init({
  clientId: "6fb511c5b5e82cb8d4c14f0ce8504c2fc9b9ed5d34a26822693926de02eab1a3",
  authUrl: "https://api.hatchfi.co/v1/login",
  userId: "bc535daf-98a2-478b-bb5f-614d11aa7a78",
});
```

## [](https://docs.hatchfi.co/hatchfi-authentication#hatchfi-backend-authentication)Hatchfi Backend Authentication

Requirements

*   *clientId *- represents your application identification (found in your project dashboard)

*   *apiKey *- found in your project dashboard

*   *secretKey *- found in your project dashboard

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





