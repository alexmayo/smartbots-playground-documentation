# avatarInfo

Returns the Second Life avatar details.

```javascript
Bot.avatarInfo("0b65a122-8f77-64fe-5b2a-225d4c490d9c").then(function(res) {
  console.log("Avatar info:", res);
});
```

Or using async/await:

```javascript
let res = await Bot.avatarInfo("0b65a122-8f77-64fe-5b2a-225d4c490d9c");
console.log("Avatar info:", res);
```

## Input

| Variable | Required | Description |
|----|----|----|
| uuid | yes | UUID of the avatar to query |

## Output

| Field | Type | Description |
|----|----|----|
| `success` | bool | true if command completed successfully |
| `error` | string | error string if command has failed |
| `about` | string | Profile text |
| `born` | string | SL birth date, `MM/DD/YYYY` |
| `identified` | string | `"1"` if avatar has payment info |
| `image` | string | Profile image UUID |
| `first_life_image` | string | First life image UUID |
| `first_life_text` | string | First life text |
| `mature` | string | `"1"` if profile is mature |
| `online` | string | `"1"` if avatar is online |
| `partner` | string | Partner UUID (zero UUID if none) |
| `publish_web` | string | `"1"` if profile is allowed to be published on the web |
| `transacted` | string | `"1"` if payment info was used |
| `url` | string | Profile URL |

## Limitations

This API command is not intended for a mass parsing. It takes about 2-3 seconds to complete, and repetitive requests (roughly more than 1 per 3 seconds) may get throttled.

Also, multiple non-stop requests may cause bot to relog.