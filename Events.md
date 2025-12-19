# Events

An event is a callback function that is invoked when something happens with your bot or the surrounding world.

Callbacks are set using the `on()` function:

```javascript
Bot.on("instant_message", function(data) {
  console.log("bot got a message:", data);
});
```

## Events Reference

| **Messaging** |
|----|
| `[chat_message](./Events/chat_message.md)` | Fires when bot receives a message in the local chat |
| `[instant_message](./Events/instant_message.md)` | Fires when bot receives a message from another avatar or in-world object |
| `[start_typing](./Events/start_typing.md)` | Fires when another avatar starts typing in IM to the bot*(Not available for QubicBot yet)* |
| `[stop_typing](./Events/stop_typing.md)` | Fires when another avatar stops typing in IM to the bot *(Not available for QubicBot yet)* |
| `[teleport_offer](./Events/teleport_offer.md)` | Fires when bot receives a teleport offer from another avatar |
| **Group Messaging** |
| `[group_offer](./Events/group_offer.md)` | Fires when bot receives a group invite |
| `[group_im](./Events/group_im.md)` | Fires when bot receives a group chat message |
| `[group_notice](./Events/group_notice.md)` | Fires when bot receives a group notice |
| **Inventory** |
| `[inventory_offer](./Events/inventory_offer.md)` | Fires when bot receives an inventory offer |
| `[balance_changed](./Events/balance_changed.md)` | Fires when bot receives or pays money |
| **Friendship** |
| `[friendship_offer](./Events/friendship_offer.md)` | Fires when bot receives a friendship offer |
| **Movement** |
| `[autopilot_completed](./Events/autopilot_completed.md)` | Fires when bot autopilot successfully completes its journey *(Not available for QubicBot yet)* |
| `[autopilot_started](./Events/autopilot_started.md)` | Fires when bot autopilot starts *(Not available for QubicBot yet)* |
| `[autopilot_stuck](./Events/autopilot_stuck.md)` | Fires when bot autopilot gets stuck and gives up moving further *(Not available for QubicBot yet)* |
| `[self_position](./Events/self_position.md)` | Fires when bot in-world location, position, or heading changes *(Not available for QubicBot yet)* |
| `[sit](./Events/sit.md)` | Fires when bot sits on an object |
| `[teleport_status](./Events/teleport_status.md)` | Fires when bot teleports, indicating various stages of the teleport *(Not available for QubicBot yet)* |
| **World** |
| `[avatar_tracker_update](./Events/avatar_tracker_update.md)` | Reports position from avatars tracked by `[trackAvatars](./Commands/trackAvatars.md)` command |
| `[region_restart](./Events/region_restart.md)` | Fires when bot receives a region restart notification *(Not available for QubicBot yet)* |
| `[region_restart_cancelled](./Events/region_restart_cancelled.md)` | Fires when bot receives a region restart cancellation notification *(Not available for QubicBot yet)* |
| `[script_dialog](./Events/script_dialog.md)` | Fires when bot receives a scripted dialog with menu buttons |
| **Online Status** |
| `[before_login](./Events/before_login.md)` | Fires when bot is going to log in to Second Life |
| `[after_login](./Events/after_login.md)` | Fires when bot successfully logs in to Second Life |
| `[before_logout](./Events/before_logout.md)` | Fires when bot is going offline |
| `[after_logout](./Events/after_logout.md)` | Fires after bot goes offline *(Not available for QubicBot yet)* |
| `[login_error](./Events/login_error.md)` | Fires when bot is unable to log in to Second Life *(Not available for QubicBot yet)* |
| **Webhooks** |
| `[playground_webhook](./Events/playground_webhook.md)` | Fires when the script's webhook receives an HTTP request from your server |