
title: Frontend Authentication
slug: 6-jBxEyzz-DkG7rt29Msy
createdAt: Tue May 31 2022 00:32:18 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 13:52:25 GMT+0000 (Coordinated Universal Time)
---

There are two ways to authenticate your users from your frontend with the Hatchfi SDK or without it. Whichever route you chose, you'll need to have your `clientId` and `userId` ready to go.

## Without Hatchfi's SDK

In order to authenticate your users with Hatchfi, you'll need to log the user in and generate a token. This is simply done by setting up an endpoint on your server that reaches out to our `/auth/login`[](https://docs.hatchfi.co/hatchfi-authentication#hg-hatchfi-frontend-authentication) endpoint.

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

## With Hatchfi's SDK

When dealing with our SDK the process is a bit easier, you'll really only need to import our SDK into your project and fill in the proper fields

*   *clientId *- represents your application identification (found in your dashboard)

*   *authUrl *- URL endpoint to authenticate against

*   *userId *- the user UUID you'd like to authenticate

```javascript
import Hatchfi from "@hatchfi/hatchfi"

// This example requires you to use our Hatchfi JS SDK
const hatchfi = Hatchfi.init({
  clientId: "6fb511c5b5e82cb8d14c14f0ce85104c2fc9b9ed5d234a263822693de02eab1a3",
  authUrl: "https://api.hatchfi.co/v1/login",
  userId: "bc235daf-98a2-478b-b45f-614d31aa7a78",
});
```






