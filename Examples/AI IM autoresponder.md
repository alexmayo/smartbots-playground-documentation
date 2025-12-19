# AI IM autoresponder

This is the source code of a simple AI autoresponder by SmartBots, available in the Bot Store.

The script listens for incoming instant messages (IMs), sends them to the SmartBots AI engine, and responds with the AI-generated reply.

```javascript
const aiSettings = {
  instructions: "You are a bot in Second Life. Act like a greater, be polite and friendly. Answer any question you can.",
};

// Init default settings

Object.assign(aiSettings, userSettings);

if (aiSettings.maxResponseTokens) {
  aiSettings.maxResponseTokens = Number(aiSettings.maxResponseTokens);
}

// console.log("AI settings:", aiSettings);

// Init AI

Bot.AI.configure(aiSettings);

// Listen for IMs

Bot.on("instant_message", (event) => {
  if (event.speaker_type != "AVATAR") { return; }
  
  processMessage(event.speaker_name, event.speaker_uuid, event.message);
});

console.log(process.name + " is running");

async function processMessage(senderName, senderUUID, message) {	
  console.log(`[IM] ${senderName}: ${message}`);
  
  Bot.startTyping(senderUUID);
  
  try {
    const convo = Bot.AI.getConversationByName(senderName);
    let res;

    try {
      res = await convo.chat(message, { featureEmptyResponse: true });
    } catch (e) {
      console.error(`AI error: ${e.message}`);
      return;
    }

    if (!res.text) { 
      console.log(`[AI] ${Bot.name}: response empty, ${res.emptyTextReason}`);
      return; 
    }

    console.log(`[AI] ${Bot.name}: ${res.text}`);
    Bot.im(senderUUID, res.text);
  } finally {
    Bot.stopTyping(senderUUID);
  }
}
```