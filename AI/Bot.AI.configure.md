# Bot.AI.configure

Configures AI options to be used in all further communications within the current script.

```javascript
Bot.AI.configure(options);
```


:::note
The `instructions` and `maxResponseTokens` settings are hard-coded in user settings. They do not need to be explicitly created for user settings. Instead, these values should be fetched from `userSettings.instructions` and `userSettings.maxResponseTokens` and included in the configuration.

:::

## Input

| Variable | Description |
|----|----|
| options | Configuration directives for the AI engine. |

### Options Format

```javascript
{
  // Main configuration instructions for the AI: role, behavior, response rules etc.
  instructions?: string;

  // If responding to a particular previous AI message of the bot
  parentMessageId?: string;

  // Maximum number of tokens to generate in response
  maxResponseTokens?: number;

  // The unique conversation id. Usually generated automatically based
  // on the sender and bot name.
  conversationId?: string;

  // The amount of history to retain for the conversation.
  maxHistoryMessages?: number;
}
```

## Output

This command does not return a value.