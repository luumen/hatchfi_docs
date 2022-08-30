
title: Hatchfi Link
slug: J0iYPrrQamojSwijXj3Uh
createdAt: Mon May 30 2022 06:50:25 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 06:03:24 GMT+0000 (Coordinated Universal Time)
---

## What is Hatchfi Link?

Hatchfi Link is our plugin modal that makes it easier for your users to connect their blockchain data to your application. Hatchfi Link gives you instant access to over 8,500 cryptocurrencies, 10+ exchanges, and wallets, and removes the hassle of maintaining those integrations yourself. Link is also available in a URL form, so you don't need to use our SDK if you don't want to or are using a different language.

**Without the Hatchfi SDK** 

First, you want to generate a session token. To do this, start by making a request to our authentication endpoint `https://api.hatchfi.co/v1/auth/login` which includes your API Key, Secret Key, and your users' Id:

```curl
curl --request POST \
    --url https://api.hatchfi.co/v1/auth/login \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

Upon success, you will receive a session token that will allow your user to access Hatchfi Link within your app and log in to their respective providers. See example return below.

```json
{
    "userId": "4e22d4b5-0cef-413f-898e-73c3eb6d4921",
    "token": "eyJhbGcg8iJIUzI1NiIsInR5cCI6Ikpghr49.eyJ1c2VySWQiOiIwMDExIiwiaWF0IjoxNjQ5NDA1NzY0LCJleHAiOjE2NDk0MDY5NjR9.l8JVJzLe2NAOSXKZsM2LQHMJrFDlCtQZqSqoSbhuHVs"
}
```

From here, you have two choices:

*   Open up an iframe with Hatchfi Link

*   Open up a new window or tab with Hatchfi Link

`https://link.hatchfi.co/?clientId={your-client-id}&token={users-session-token}`

And that is it! You'll be able to start using Hatchfi Link in your app to connect your users' crypto accounts!

## [](https://docs.hatchfi.co/hatchfi-link#customizing-link)Customizing Link

> Coming Soon

## [](https://docs.hatchfi.co/hatchfi-link#how-to-use-link)How to use Link

**With the Hatchfi SDK**

> Coming Soon





