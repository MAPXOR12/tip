![npm install](https://nodei.co/npm/vcodes.js.png?mini=false)<br/>
[Do you need my help? Visit our Discord server.](https://vcodes.xyz/discord)

# Installation
```console
npm i tip --save
yarn add tip
```


# Usage
```js
const tip = require('./tip.index');
const dbl = new vCodes("tip Bot Token");


dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on vCodes.`)
    dbl.checkVote("714451348212678658").then(value => console.log("Vote Control: "+ value))

    /*
        let guildCount = 1234;
        let shardCount = 5;
        dbl.stats(guildCount, shardCount, () => console.log("Stats updated on vCodes."));
    */
})


/*
    Get with Bot: 
    dbl.on("vote", ({ user, bot }) => {
        console.log(`${user.username} voted ${bot.username}`)
    })
*/
dbl.on("vote", ({ user }) => {
    console.log(`${user.username} voted.`)
})
```

# Detailed

### Define Module
```js
const tip = require('./tip.index.js);
const dbl = new vCodes("tip Bot Token");
```

### Let's add an event to see if it works.
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on tip.`)
})

// => Bot named Allegro successfully finded on tip.
```

### Let's update bot data
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on tip.`)
    let guildCount = 1234;
    let shardCount = 5;
    dbl.stats(guildCount, shardCount, () => console.log("Stats updated on tip."));
})

// => Bot named Allegro successfully finded on tip.
// => Stats updated on tip.
```

### Let's check if a user has voted.
```js
dbl.on("ready", (bot) => {
    console.log(`Bot named ${bot.username} successfully finded on tip.`)
    dbl.checkVote("714451348212678658").then(value => console.log("Vote Control: "+ value))

    /*
        let guildCount = 1234;
        let shardCount = 5;
        dbl.stats(guildCount, shardCount, () => console.log("Stats updated on tip."));
    */
})

// => Bot named Allegro successfully finded on tip.
// => Vote Control: false
```

### Let's check if there is a user who voted for our bot instantly.
```js
dbl.on("vote", ({ user }) => {
    console.log(`${user.username} voted.`)
})

// => mapxor voted.
```
```js
// WITH BOT
dbl.on("vote", ({ user, bot }) => {
    console.log(`${user.username} voted ${bot.username}`)
})

// => mapxot voted Allegro.
```

---

