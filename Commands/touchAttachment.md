# touchAttachment

Touches an attachment of the bot (HUD or wearable object).

```javascript
Bot.touchAttachment(objectName, linkNumber);
```

## Input

| Variable | Required | Description |
|----|----|----|
| `objectName` | yes | The name of the object to touch. |
| `linkNumber` | yes | The link number of the prim (root prim = 1). |

## Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully. |
| `error` | string | Error string if command has failed. |

## Return value

* If the object is not found, the bot returns `result.success = false` and an error message in `result.error` (use `.then(function(result)` to catch this).
* If `linkNumber` is invalid (less than 1 or greater than the number of child prims), the function returns success but no touch occurs.

## Comments

Remember that the bot must load all objects from Second Life before touching them. Therefore:

* After logging in, give the bot about 30 seconds to load surrounding objects.
* Do the same after teleporting.

### Determining the link number ![](uploads/fe746996-bd68-4ba8-a15e-e239ddd741be/7f170daa-e552-4428-83d7-67eaf2918ef4/Get_object_linknum.jpg "right-50 =294x264")

The root prim is always `1` (so `linkNumber = 1` for single-prim objects as well).

To get the link number of a specific child prim, use the **Phoenix Firestorm Viewer**:


1. Start editing your object.
2. Check the "Edit linked" option.
3. Select the required child prim.
4. See the "Link number" value.

## Examples

Touch a special test attachment object (contact SmartBots support to get it):

```javascript
// Touch the button of the "Touch tester v2.0" object:
Bot.touchAttachment("Touch tester v2.0", 2);

// Gracefully exit since we're done

exit();
```