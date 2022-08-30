
title: Handling Connections
slug: nkvh-handling-connections
createdAt: Sun Aug 21 2022 17:52:51 GMT+0000 (Coordinated Universal Time)
updatedAt: Sun Aug 21 2022 17:54:00 GMT+0000 (Coordinated Universal Time)
---

The primary way Hatchfi Link is used is via iframe; as a result, we use the [Post Message API](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage) to pass information about the connection. To listen for a connection success or failure, you'll need to set up an [event listener](https://developer.mozilla.org/en-US/docs/Web/API/Window/message_event) to listen for a message.

### Listener Example

```javascript
// This can live in your mounting method or anywhere of your preference.

window.addEventListener("message", (event) => {
    if (event.data.hatchfi) {
      if (event.data.result.status == "success") {
        // Handle successful connection
      } else if (event.data.result.status == "error") {
        // Handle failed connection
      } else {
        // handle link being closed
      }
    }
  });
```

### Successful Connection

```javascript
parent.postMessage(
    {
        hatchfi: true,
        result: { data: res.data, status: "success" },
    },
    "*"
);
```

### Failed Connection

```javascript
parent.postMessage(
    {
        hatchfi: true,
        result: { data: null, status: "close" },
    },
    "*"
);
```

### Close Link

```javascript
parent.postMessage(
    {
        hatchfi: true,
        result: { data: null, status: "close" },
    },
    "*"
);
```

