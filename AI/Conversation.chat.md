# Conversation.chat

Sends a chat message request to the bot AI within a conversation with a specific resident.

```javascript
Conversation.chat(message[, options]);
```


:::note
The `instructions` and `maxResponseTokens` settings are hard-coded in user settings. They do not need to be explicitly created for user settings. Instead, these values should be fetched from `userSettings.instructions` and `userSettings.maxResponseTokens` and included in the configuration.

:::

## Input

| Variable | Description |
|----|----|
| message | The chat message to send to the bot. |
| options | *(optional)* Configuration directives for the AI engine. Example: |

```javascript
{
  // Main configuration instructions for the AI: role, behavior, response rules etc.
  instructions?: string;

  // Maximum number of tokens to generate in response
  maxResponseTokens?: number;

  // Max number of response bytes (SL IM has a max limit of 1023 bytes)
  maxResponseBytes?: number;
}
```

## Output

| Variable | Description |
|----|----|
| result | Returns the same value as `[Bot.AI.chat(...)](./Bot.AI.chat.md)`. |


\