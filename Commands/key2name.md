# key2name

Returns the avatar's Second Life name by UUID. This command works in opposition to `[name2key](./name2key.md)`.

```javascript
Bot.key2name(key);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `key` | yes | The UUID of the avatar |

## Output

| Variable | Type | Description |
|----|----|----|
| `slname` | string | Second Life name of the avatar |

## Examples

```javascript
var slname = "Glaznah Gassner";

Bot.name2key(slname)
  .then(function(result) {
    if (result.success) {
      console.log("The UUID of " + slname + " is " + result.slkey);
    } else {
      console.log("Error executing name2key: " + result.error);
    }
	
    return Bot.key2name(result.slkey);
  })
  .then(function(result) {
    console.log("Backward key2name check. Name: " + result.slname);
  });
```