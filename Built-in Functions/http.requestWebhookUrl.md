# http.requestWebhookUrl

Allocates a new, per-run webhook URL and authorization token for the current script instance.

```javascript
const webhook = await http.requestWebhook();
```

# Input

This function does not accept any input parameters.

# Output

This function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | boolean | True if the command completed successfully. |
| `error` | string | Error message if the command failed. |
| `url` | string | Endpoint that accepts your server's POST requests. |
| `token` | string | Bearer token you must include in the Authorization header. |

# Comments

It is good practice to register the event listener **before** requesting the webhook.\nPlace `Bot.on("playground_webhook", …)` before calling `http.requestWebhook()` to avoid missing early responses.

Webhook URL and token are unique for each script run — they change ("release") on every script restart.\nEnsure these values are delivered to your remote server after obtaining them.

Subsequent calls to `http.requestWebhook()` within the same script return the **same** URL and token.\nThese values persist while the script is running.\nThere are no system-wide limits on the number of webhooks (unlike `llRequestURL`).

For details on using the webhook, see the **playground_webhook** event documentation.

# Examples

A simple demonstration of obtaining a webhook URL and token, and listening for the `playground_webhook` event:

```javascript
// Event should be placed first, to catch any early requests.
Bot.on("playground_webhook", (event) => {
  console.log("Webhook request received:", event);
});

// Request the webhook URL and token.
const webhook = await http.requestWebhook();  
console.log("Webhook:", webhook);
```

Check the complete example script and scenario for more detailed usage.