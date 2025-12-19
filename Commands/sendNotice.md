# sendNotice

Sends a notice to a group.

```javascript
Bot.sendNotice(groupuuid, subject, text, attachment);
```

# Input

| Variable | Required | Description |
|----|----|----|
| `groupuuid` | yes | The UUID of the group. |
| `subject` | yes | The subject of the notice (cannot contain international characters). |
| `text` | yes | The text of the notice (can contain international characters). |
| `attachment` | optional | The inventory UUID of the attachment (see **Attachments** below). |

# Output

Function returns a Promise with the following data:

| Variable | Type | Description |
|----|----|----|
| `success` | bool | True if command completed successfully |
| `error` | string | Error string if command has failed |

# Comments

* This command does **not** return `FAIL` if your bot lacks the "Send Group Notice" ability. Make sure the bot has the required group permissions before using this command.
* The notice delivery is guaranteed even if the bot is offline (the notice will be sent once the bot comes online).

# Attachments

The notice attachment can be taken from the bot's inventory. To create an attachment, follow these steps:


1. Set **copy + transfer** permissions on the object (so the bot can give it with the notice).
2. Drop the object onto the bot in Second Life.
3. Open your **SmartBots account**, click **"Manage Bot."**
4. Open the bot's **inventory browser.**
5. Copy the **inventory UUID** of the desired inventory item.