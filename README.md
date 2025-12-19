# SmartBots Playground Documentation
This repo contains all public documentation for the SmartBots Playground API.

SmartBots Bots Playground is a JavaScript sandbox to run your own programs to control your SmartBot.

The Bots Playground is available here: play.mysmartbots.com

## Controlling bots with JavaScript

 ![](/api/attachments.redirect?id=ba7e2730-41db-4c5f-8aaa-522a7ddb8e08 " =2876x1334")

Playground runs programs written JavaScript. The pure javascript: with callbacks, functions, arrays and objects. The underlying javascript engine is NodeJS.

There are some limitations applied yet:

* We do not support ECMAScript 6
* import/export is disabled
* you can't include one script into another (yet)

## Interacting with your bot

Your program runs in a sandbox and sends commands to the bot. Events come from the bots to your program.

This two-way communication is tied directly into javascript program routines:

* Bot commands are functions you call
* Events are callback functions you specify

Refer to the Examples page for more info.

## Read more

* Playground FAQ
* Bug Hunter program
* Create and sell Playground scripts
