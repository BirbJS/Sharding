[![huntr](https://cdn.huntr.dev/huntr_security_badge_mono.svg)](https://huntr.dev)

[![NPM](https://nodei.co/npm/@birbjs/sharding.png)](https://nodei.co/npm/@birbjs/sharding)

# @BirbJS/Sharding
Birb.JS is a Discord API wrapper for JavaScript and TypeScript (we include built-in type declarations). It’s built to be simple, yet powerful. With just a few lines of code, you can get a Discord bot connected to the Discord API. **Birb.JS is still in development. It is highly recommended you don’t use it until it’s ready.**

## Links
[Documentation](https://birb.js.org/addons/sharding)    
[GitHub Repo](https://github.com/BirbJS/Sharding)    
[NPM Page](https://npmjs.com/package/@birbjs/sharding)

## Installation
Birb.JS is listed on [npm](https://www.npmjs.com/package/@birbjs/sharding)! You can install it by running `npm install @birbjs/sharding --save`.

## Example
Your bot's main client file (bot.js):
```js
const { Client, Intents } = require('birb');
const client = new Client({
    intents: new Intents(Intents.FLAGS.ALL)
});

client.listen('ready', () => {
    console.log('Connected to Discord!');
});

client.connect('your_bot_token');
```
Your bot's new sharding file (index.js):
```js
const { ShardMaster } = require('@birbjs/sharding');
const sharder = new ShardMaster({
    token: 'your_bot_token'
});

sharder.listen('shardReady', (shardId) => {
    console.log(`Shard #${shardId} is ready!`);
});

sharder.start();
```

## Licensing
Birb.JS is currently licensed under the [Mozilla Public License 2.0](https://github.com/BirbJS/Birb/blob/main/LICENSE). You're free to use it as a library in both personal and commercial projects, free-of-charge.
