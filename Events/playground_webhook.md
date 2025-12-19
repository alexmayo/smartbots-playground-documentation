# playground_webhook

Fires when the script's webhook receives an HTTP request from your server.

```javascript
Bot.on("playground_webhook", function(event) { ... });
```

## Reference

This event comes with the following event object:

| Variable | Description |
|----|----|
| name | The name of the event |
| bot_slname | Your bot's Second Life name (e.g. `"smartbots Resident"`) |
| hookId | Identifier of the current webhook (also visible at the end of the request URL) |
| correlationId | A unique identifier for this request |
| payload | Parsed JSON data from the request |

## Important notes

* If the payload on the request is not valid JSON, the `payload` object will come through as an empty object.
* To send a string payload, set `Content-Type: text/plain` on the remote server.
* It's best practice to place the event listener **above** the `[http.requestWebhookUrl()](./../Built-in%20Functions/http.requestWebhookUrl.md)` command to catch any early requests.

## Example

```javascript
Bot.on("playground_webhook", (event) => {
  console.log("Webhook received:", event);
});
```

## Sending a request from a remote server

Send a POST request to the webhook URL, including the `Authorization` and `Content-Type` headers. The payload is JSON:

```bash
curl --location 'https://gate07.play.mysmartbots.com/userhook/ca4687a9-db28-43ee-9bb8-cf80100t41cf' \
  --header 'Content-Type: application/json' \
  --header 'Authorization: Bearer PBubZ9CbPd9PWUm2n6L5ygfHkhCOUf8V' \
  --data '{"exampleData": 123456}'
```

Use `--header 'Content-Type: text/plain'` to send a string payload instead of JSON.

### Example response

```json
{
  "success": true,
  "correlationId": "bb980f2e-b3e0-4eee-acd0-f5041af6a449"
}
```

### Example `playground_webhook` event

```json
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