# Webhooks

This example demonstrates how to use a webhook in the Bot Playground, including:


1. Creating a webhook
2. Displaying webhook details
3. Sending data from a remote server
4. Receiving and handling that data in your script

## Playground Script

```javascript
Bot.on("playground_webhook", (event) => {
  console.log("Webhook received:", event);
});

// 1. Create a webhook

const webhook = await http.requestWebhook(); // Requests the webhook URL and token

// 2. Display its data
// (You would typically send this to your server, but here we just display it)
console.log("Webhook details:", webhook);
```

### Example Output

```
Webhook details:
{
  url: "https://gate07.play.mysmartbots.com/userhook/ca4687a9-db28-43ee-9bb8-cf80100t41cf",
  token: "PBubZ9CbPd9PWUm2n6L5ygfHkhCOUf8V"
}
```

## Remote Server Simulation (cURL)

Use the following `curl` command to simulate sending data from a remote server:

```bash
curl --location 'https://gate07.play.mysmartbots.com/userhook/ca4687a9-db28-43ee-9bb8-cf80100t41cf' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer PBubZ9CbPd9PWUm2n6L5ygfHkhCOUf8V' \
  --data '{"exampleData": 123456}'
```

### Example Output

```
{
  "success": true,
  "correlationId": "bb980f2e-b3e0-4eee-acd0-f5041af6a449"
}
```

## Playground Webhook Output

When the webhook receives data, the script logs the following event:

```
Webhook received:
{
  "name": "playground_webhook",
  "bot_slname": "smartbot Resident",
  "hookId": "ca4687a9-db28-43ee-9bb8-cf80100t41cf",
  "correlationId": "bb980f2e-b3e0-4eee-acd0-f5041af6a449",
  "payload": {
    "exampleData": 123456
  }
}
```