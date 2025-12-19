# isOnline

Returns `true` or `false` depending on whether the bot is online.

```javascript
const res = await Bot.isOnline();
console.log("Is Bot Online:", res);
```

## Input

This function does not require any arguments.

## Output

| Variable | Type | Description |
|----|----|----|
| `return value` | boolean | `true` if the bot is online, `false` otherwise |

## Examples

```javascript
let isOnline = await Bot.isOnline();
if (isOnline) {
  console.log(`Bot is Online`);
} else {
  console.log(`Bot is Offline`);
}
```