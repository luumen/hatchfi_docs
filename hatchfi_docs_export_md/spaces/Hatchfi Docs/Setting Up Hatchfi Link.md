
title: Setting Up Hatchfi Link
slug: 8Uku-setting-up-hatchfi-link
createdAt: Sun Aug 21 2022 17:33:54 GMT+0000 (Coordinated Universal Time)
updatedAt: Sun Aug 21 2022 17:52:39 GMT+0000 (Coordinated Universal Time)
---

First, you want to generate a session token. To do this, start by requesting our authentication endpoint `https://api.hatchfi.co/v1/auth/login` which includes your API Key, Secret Key, and your users' Id:

```curl
    curl --request POST \
    --url https://api.hatchfi.co/v1/auth/login \
    --header 'X-Hatchfi-Api: API_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-Secret: SECRET_KEY_FROM_DASHBOARD' \
    --header 'X-Hatchfi-User-Id: USER_ID'
```

Upon success, you will receive a session token allowing your user to access Hatchfi Link within your app and log in to their respective providers. See an example return below.

```json
{
    "userId": "4e22d4b5-0cef-413f-898e-73c3eb6d4921",
    "token": "eyJhbGcg8iJIUzI1NiIsInR5cCI6Ikpghr49.eyJ1c2VySWQiOiIwMDExIiwiaWF0IjoxNjQ5NDA1NzY0LCJleHAiOjE2NDk0MDY5NjR9.l8JVJzLe2NAOSXKZsM2LQHMJrFDlCtQZqSqoSbhuHVs"
}
```

From here, you will take your `clientId` and your newly generated `token` and pass them into the URL below.&#x20;

## Building the URL

Building Hatchfi Link's URL is quick and easy. You'll start with the required parameters.

```none
https://link.hatchfi.co/?clientId={your-client-id}&token={users-session-token}
```

### Hatchfi Link Redirect

If you'd like to redirect your users and you've provided a redirect URL in your project settings, you can append `&redirect=true` to the URL string.

```none
https://link.hatchfi.co/?clientId={your-client-id}&token={users-session-token}&redirect=true
```

### Hatchfi Link Pre-determined Provider

In many cases, you may just want to guide your users through a pre-determined provider connection. With Hatchfi Link, you can easily pass `&provider=name` into the URL string.

```none
https://link.hatchfi.co/?clientId={your-client-id}&token={users-session-token}&provider=polygon
```

### Complete Hatchfi Link Example

```none
https://link.hatchfi.co/?clientId={your-client-id}&token={users-session-token}&redirect=true&provider=polygon
```



And that is it! You'll be able to start using Hatchfi Link in your app to connect your users' crypto accounts.

