# AI

[SmartBots AI](https://docs.mysmartbots.com/s/ai/) is a conversation-based AI system designed to work with Playground scripts, enabling bots to conduct contextual, conversational interactions.

## SmartBots AI for Developers

The most convenient way to use SmartBots AI is through **conversations**.

While you can send raw requests to the AI, conversations allow you to maintain context across messages and responses.

* Create a conversation using `[Bot.AI.getConversationByName(residentName)](./AI/Bot.AI.getConversationByName.md)`.
* The resulting conversation object can be reused for subsequent messages.
* SmartBots AI keeps track of context within a conversation.
* Conversation options can be configured individually for each conversation.
* Conversations are **system-wide**, tied to a **script + bot + specific resident**.

## Main Concepts

### Instructions

Rules for the bot: how it should react, how to role-play, and what knowledge it should have. (See examples in **Instructions** section.)

### Token

Each request to SmartBots AI consumes tokens. Read more about token usage.

## AI Commands Reference

| **Commands** |
|----|
| `[Bot.AI.chat](./AI/Bot.AI.chat.md)` | Sends a chat message request to the bot AI. |
| `[Bot.AI.configure](./AI/Bot.AI.configure.md)` | Configures AI options to be used in all further communications within the current script. |
| `[Bot.AI.getConversationByName](./AI/Bot.AI.getConversationByName.md)` | Gets or creates a conversation with a specific resident. If it doesn't exist, it will be created. |
| `[Bot.AI.forgetConversation](./AI/Bot.AI.forgetConversation.md)` | Forgets (cancels) a conversation between the bot and a specific resident. |
| **Conversation Commands** |
| `[Conversation.chat](./AI/Conversation.chat.md)` | Sends a chat message request to the bot AI within a conversation with a specific resident. |
| `[Conversation.configure](./AI/Conversation.configure.md)` | Sets configuration values for future usage. |