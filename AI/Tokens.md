# Tokens

A token is a "charge" used by the SmartBots AI engine. You can think of a token as roughly equivalent to a short word (\~4 characters). Longer words and phrases may consume more than one token.

When your script calls SmartBots AI, tokens are consumed from the script owner's balance.\nIf you sell your script through the Bot Store, your buyers will need to maintain their own token balance.\n


:::tip
As of October 2023, each user receives 20,000 free tokens.

:::

## Tokens usage

Tokens are consumed for several parts of each AI request:

* User message – what the resident says to the bot
* Instructions – the system prompt that defines the bot's behavior
* Conversation history – previous messages and responses (to maintain context)

## Usage example

### **First message**

* Resident: `"Hello!"`
* Request sent: `Your instructions` + `"Hello"`
* Bot response: `"Hi!"`

> **Token usage:**\n1 (message) + 2 (instructions) + 1 (response) = **4 tokens**

### **Second message**

* Resident: `"Who are you?"`
* Request sent: `Your instructions` + `"Hello"` + `"Hi!"` + `"Who are you?"`
* Bot response: `"I am a bot."`

> **Token usage:**
>
> 3 (message) + 2 (instructions) + 4 (history) + 4 (response) = **13 tokens**


:::info
In reality, the token count will be slightly higher because the system also includes metadata such as the bot's name, the resident's name, and other system data.

:::

## Tokens report

AI functions such as `[Conversation.chat()](./Conversation.chat.md)` return a token usage report and the remaining token balance.\nYou can use this information to notify script owners when their balance is running low.