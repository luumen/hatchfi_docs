
title: Hatchfi Providers
slug: M28JSwpYn_t72QuXfCRQF
createdAt: Mon May 30 2022 06:29:11 GMT+0000 (Coordinated Universal Time)
updatedAt: Tue May 31 2022 06:03:24 GMT+0000 (Coordinated Universal Time)
---

Hatchfi's Providers can be queried to receive metadata about each provider. There are two public endpoints available.

## All Providers

To query all of our providers, we have the `/providers` endpoint that returns our current providers list, their access requirements, and additional metadata for each one.

:::codeblocktabs
```curl
curl --request GET \
  --url https://api.hatchfi.co/v1/providers
```

```python
import http.client

conn = http.client.HTTPSConnection("api.hatchfi.co")

payload = ""

conn.request("GET", "/v1/providers", payload)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
import axios from "axios";

const options = {method: 'GET', url: 'https://api.hatchfi.co/v1/providers'};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

```javascript
const providers = await hatchfi.providers.getAll();
```
:::

Here is a snippet of what the return value looks like:

```json
[
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
  },
  {
    scopes: [],
    currencies: [],
    inputs: ["api_key", "secret_key"],
    notes: "Please enter your API and Secret Key.",
    resourceType: "provider",
    name: "gemini",
    displayName: "Gemini",
    logo: "https://hatchfi.co/providers/gemini.png",
    authType: "token",
  },
  ...
]
```

## [](https://docs.hatchfi.co/hatchfi-providers#specific-provider)Specific Provider

Our single provider endpoint allows you to easily query our API to view a single provider's information. You can pass the provider name into the method to get data specific to that provider.

This endpoint returns the specified provider that you've requested

:::codeblocktabs
```curl
curl --request GET \
  --url https://api.hatchfi.co/v1/providers/:providerId
```

```python
import http.client

conn = http.client.HTTPSConnection("api.hatchfi.co")

payload = ""

conn.request("GET", "/v1/providers/:providerId", payload)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```javascript
import axios from "axios";

const options = {method: 'GET', url: 'https://api.hatchfi.co/v1/providers/:providerId'};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

```javascript
const provider = await hatchfi.providers.getOne("gemini");
```
:::

Here is a snippet of what the return value looks like:

```json
[
  {
    scopes: [],
    currencies: [],
    inputs: ["api_key", "secret_key"],
    notes: "Please enter your API and Secret Key.",
    resourceType: "provider",
    name: "gemini",
    displayName: "Gemini",
    logo: "https://hatchfi.co/providers/gemini.png",
    authType: "token",
  },
]
```

:::hint
ℹ️ Please note that you must pass in the name value and not displayName, otherwise you'll get a 404 response.
:::

***

## [](https://docs.hatchfi.co/hatchfi-providers#request-or-become-a-provider)Request or Become a Provider

Not seeing a provider you or your users need? Do you want to become a Hatchfi Provider?

If so, please fill out the [Hatchfi Provider Request](https://airtable.com/shrRQjpKdHukYPRfF) form. Alternatively, you can use our [roadmap](https://hatchfi.canny.io/provider-request) to request Providers and other feature requests.





