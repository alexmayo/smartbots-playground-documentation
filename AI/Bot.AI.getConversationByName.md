# Bot.AI.getConversationByName

Gets or creates a conversation with a specific resident. If the conversation does not exist yet, a new one will be created.

```javascript
Bot.AI.getConversationByName(residentName);
```

## Input

| Variable | Description |
|----|----|
| residentName | The Second Life name of the resident. |

## Output

| Variable | Description |
|----|----|
| result | A conversation object that can be used to send and manage chat messages with the specified resident. |

## Example

```javascript
const conversation = await Bot.AI.getConversationByName("Glaznah Gassner");

// Send a message within this conversation
await conversation.chat("Hello! How are you today?");
```