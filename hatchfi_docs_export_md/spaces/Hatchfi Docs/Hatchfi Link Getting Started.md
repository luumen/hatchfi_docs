
title: Hatchfi Link Getting Started
slug: gaNI-hatchfi-link-getting-started
createdAt: Sun Aug 21 2022 17:07:01 GMT+0000 (Coordinated Universal Time)
updatedAt: Sun Aug 21 2022 19:03:03 GMT+0000 (Coordinated Universal Time)
---

Hatchfi Link is a plug-and-play front-end component that helps you streamline the onboarding experience of your customers' crypto data.&#x20;

Hatchfi Link will handle credential validation via Oauth, API credentials, and wallet addresses. Hatchfi Link will also perform error handling for each provider integration that we support. Hatchfi Link can be implemented within an [iframe ](https://www.w3schools.com/tags/tag_iframe.asp)or as a stand-alone browser tab. Hatchfi Link also supports and works across all modern browsers and platforms.

## Parameters

Hatchfi Link takes four parameters; however, only two are required.

| Parameter        | Value                           | Required |
| ---------------- | ------------------------------- | -------- |
| `clientId`       | The client ID of your project   | yes      |
| `token`          | The user's session token        | yes      |
| `redirect`&#x20; | A boolean value&#x20;           | no       |
| `provider`&#x20; | A pre-determined providers name | no       |

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

In many cases, you may just want to guide your users through a pre-determined provider connection. With Hatchfi Link, you can easily do this by passing `&provider=name` into the URL string.

```none
https://link.hatchfi.co/?clientId={your-client-id}&token={users-session-token}&provider=polygon
```

### Complete Hatchfi Link Example

```none
https://link.hatchfi.co/?clientId={your-client-id}&token={users-session-token}&redirect=true&provider=polygon
```

