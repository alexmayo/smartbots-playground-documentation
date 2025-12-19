# groupInfo

Returns the Second Life group details.

```javascript
Bot.groupInfo("0b65a122-8f77-64fe-5b2a-225d4c490d9c").then(function(res) {
  console.log("Group info:", res);
});
```

## Input

This function does not require any arguments other than the group UUID.

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `charter` | string | Group text |
| `insignia` | string | Group profile image UUID |
| `fee` | number | Group join fee |
| `founder` | string | Founder avatar UUID |
| `mature` | string | `"1"` if the group has a Mature flag |
| `members` | number | The number of members |
| `member_title` | string | The default member tag |
| `name` | string | Group name |
| `open` | string | `"1"` if the group is open to join |
| `uuid` | string | Group UUID |

## Limitations

This API command is not intended for a mass group parsing. Thus, repetitive requests (roughly more than 3 per 10 seconds) may be throttled.