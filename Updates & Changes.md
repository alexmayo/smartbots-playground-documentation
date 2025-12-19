# Updates & Changes

This page lists all recent updates, new features, and improvements made to the SmartBots Playground API, editor, and more.


:::info
If you have any questions, or notice something that we've missed, please contact [Alexander Pixels](https://secondlife:///app/agent/4d9ce772-d3ee-4cce-9555-bfb06ffcb228/about) in-world.

:::


---

# October 2025 Update

This update brings a bundle of new features — including new commands, docs, and an updated editor with **autocomplete**!

### These pretty new docs! 🤩

We've spent some time updating the documentation for our APIs. After years of hosting our docs on MediaWiki, we've transitioned to a new, modern platform. We hope you like it!

### Added: `[Bot.trackAvatars(uuidList)](./Commands/trackAvatars.md)`

Allows tracking of avatar positions as they change.

* Tracking automatically stops when the bot logs out — it's recommended to call this within the `after_login` event.
* Supports tracking up to **8 avatars simultaneously**.
* All tracked avatars must be in the **same region**.

### New Event: `[avatar_tracker_update](https://a)`

Triggered whenever a tracked avatar's position changes.

* Returns detailed information including: **Name**, **UUID**, **Position**, **Heading** (radians), **Region**, **XYZ coordinates**, and **Sitting state**.
* It's recommended to register this event **before** calling `[Bot.trackAvatars](./Commands/trackAvatars.md)` to avoid missing initial updates.

### Added: `[Bot.turnTo(deg)](./Commands/turnTo.md)`

Turns the bot to face a specified direction.

* Since Second Life doesn't turn the bot if the direction change is less than 20°, the bot moves slightly to force an update.
* Due to SL limitations, turning accuracy isn't perfect, but is rarely off by more than **5°**.

### Updated Code Editor

* Added **autocomplete** for faster script editing.
* Added **auto-indenting** for cleaner and more consistent formatting.
* Redesigned **Script Settings Menu** with improved layout and easier navigation.



---


# August 2025 Update

We're excited to announce a powerful new feature for Bots Playground: incoming webhooks - giving your scripts the ability to receive data directly from your servers.

This unlocks a whole new level of integration and automation between your external systems and Second Life bots.

### Webhooks: How it works

The update introduces two new pieces:

* **Function:** `[http.requestWebhookUrl()](./Built-in%20Functions/http.requestWebhookUrl.md)` - creates a webhook endpoint your script can listen on.
* **Event:** `[playground_webhook](./Events/playground_webhook.md)` - triggered whenever your webhook receives a request.

If you're familiar with LSL, they work similarly to `llRequestSecureURL` and the `http_request` event - but now fully available in Playground.

```javascript
const webhook = await http.requestWebhookUrl();

Bot.on("playground_webhook", (event) => {
  console.log("Data received:", event);
});
```

### Webhooks: What you can do

Incoming webhooks open up endless possibilities:

* **Receive remote commands** - trigger in-world actions from your external apps or scripts.
* **Integrate with third-party services** - connect to platforms like Discord, Slack, or custom APIs.
* **Create two-way communication bridges** - link your web services and Second Life bots seamlessly.

This is a major step toward deeper automation and smarter, event-driven bot behavior. Go ahead - connect your scripts to the outside world!