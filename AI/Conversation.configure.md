# Conversation.configure

Sets some configuration values for future use.

```javascript
Conversation.configure(options);
```


:::note
The `instructions` and `maxResponseTokens` settings are hard-coded in user settings. They do not need to be explicitly created for user settings. Instead, these values should be fetched from `userSettings.instructions` and `userSettings.maxResponseTokens` and included in the configuration.

:::

## Input

| Variable | Description |
|----|----|
| options | Configuration directives for the AI engine. Example: |

```javascript
{
  // Main configuration instructions for the AI: role, behavior, response rules etc.
  instructions?: string;

  // Maximum number of tokens to generate in response
  maxResponseTokens?: number;

  // The amount of history to retain for the conversation
  maxHistoryMessages?: number;
}
```

## Output

This command does not return a value.