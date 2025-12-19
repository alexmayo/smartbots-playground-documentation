# listGroups

Returns a list of the Second Life groups the bot is a member of.

```javascript
Bot.listGroups().then(function(result) { ... });
```

## Input

This function does not require any arguments.

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |
| `groups` | object | Object containing all groups in the format: |

```json
{
  "uuid-1": "group-name-1",
  "uuid-2": "group-name-2"
}
```


:::info
**Note:** The order of the groups list is always random.

:::

## Examples

### List all groups

Print all bot groups:

```javascript
Bot.listGroups()
.then(function(result) {
  var list = "";
  
  for (var k in result.groups) {
    list = list + k + ": " + result.groups[k] + "\n";
  }
  
  console.log(list);
  exit();
});
```

### Example output

```
022df06c-b616-d400-fd94-8ccc523c5ae2: Get Paid in Second Life

9590cad7-3b63-88d6-0d06-d75b04698ec1: PicMe Poses

0ec6f039-1a39-339c-3c68-e31ed2dc703f: Earn2Life.com Discount Shops
```

See also the [example](./../Examples/Random%20group%20tag%20activator.md) in the Playground Examples section.