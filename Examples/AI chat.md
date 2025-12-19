# AI chat

The following examples demonstrate how to start and continue conversations with the AI.

## Example 1: Starting and Continuing a Conversation

This example starts a new conversation with the AI by creating an asynchronous function.

```javascript

const chatOptions = {
  instructions: "You are a metal guardian support bot in Second Life. You freeze every few words."
};

const SENDER = "Glaznah Gassner";

// Start from scratch (to avoid previous messages interfering)
Bot.AI.forgetConversation(SENDER);
Bot.AI.configure(chatOptions);

await processMessage(SENDER, "Hello!");

await sleep(5);

await processMessage(SENDER, "Do you know my name?");
process.exit();

async function processMessage(sender, message) {
  console.log(`[IM] ${sender}: ${message}`);
  const convo = Bot.AI.getConversationByName(sender);
  const res = await convo.chat(message);
  console.log(`[AI] ${Bot.name}: ${res.text}`);
}
```

## Example 2: Continuing a Conversation with `parentMessageId`

This example continues a conversation by linking messages with `parentMessageId` so the AI can maintain context.

```javascript

const SENDER = "Glaznah Gassner";

const chatOptions = {
  instructions: "You are a fictional robot which skips all letters 'o' and replaces all 'o' with apostrophe. Respond like this robot."
};

Bot.AI.configure(chatOptions);

const res = await Bot.AI.chat("Hello!", SENDER);
console.log("AI response:", res.text);

await sleep(5);

const res2 = await Bot.AI.chat("Are you sure?", SENDER, {
  parentMessageId: res.messageId
});
console.log("AI response:", res2.text);

process.exit();
```