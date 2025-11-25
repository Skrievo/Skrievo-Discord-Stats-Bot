# Skrievo Discord Stats Bot

A fully configurable **Discord Stats Bot** that automatically tracks and updates server statistics in designated channels. Perfect for keeping your community informed in real-time.

---

## 🚀 Features

* Track members with specific roles
* Count channels in categories
* Count messages in channels
* Track general guild stats: users, boosts, roles, channels, emojis, bans, invites
* Customizable activity status
* Multi-channel support
* Fully configurable via `.env` and `config.js`

---

## 📦 Installation

### 1️⃣ Install Dependencies

```bash
npm install
```

### 2️⃣ Create a `.env` File

Create a `.env` file in the project root and add:

```
TOKEN=yourbottoken
```

---

## ⚙️ Configuration

All bot settings are in `config.js`. Replace IDs and URLs with your own.

```js
const config = {}
require('dotenv').config()

// Discord Guild ID
config.guildid = 'YOUR_GUILD_ID'

// Bot Settings
config.bot = {
    token: process.env.TOKEN, // Bot token from .env
    user: { enabled: false, name: "Stats Bot", avatar: "BOT_AVATAR_URL" },
    activity_enabled: true,
    activitys: [
        { name: "through the matrix", type: "Watching", status: "idle" },
        { name: "with your data", type: "Playing", status: "dnd" },
        { name: "in your life", type: "Competing", status: "online" }
    ],
    intervall: 10 * 1000 // Activity update interval
}

// Stats Settings
config.stats = {
    intervall: 5 * 60 * 1000, // Stats update interval (min 5 min)

    roles: [
        { enabled: true, name: "👑︱Customers: {counter}", role: "ROLE_ID_HERE", channel: "CHANNEL_ID_HERE" }
    ],

    channels: [
        { enabled: true, name: "🎫︱Tickets: {counter}", categorys: ["CATEGORY_ID_1", "CATEGORY_ID_2"], channel: "CHANNEL_ID_HERE" }
    ],

    messages: [
        { enabled: true, name: "🙏︱Feedbacks: {counter}", channel_of_messages: "CHANNEL_ID_TO_OBSERVE", channel: "CHANNEL_ID_HERE" }
    ],

    guild: {
        users: { enabled: true, name: "👥︱Users: {counter}", channel: "CHANNEL_ID_HERE" },
        boosts: { enabled: true, name: "💕︱Boosts: {counter}", channel: "CHANNEL_ID_HERE" },
        roles: { enabled: false, name: "👑︱Roles: {counter}", channel: "CHANNEL_ID_HERE" },
        channels: { enabled: false, name: "🎫︱Channels: {counter}", channel: "CHANNEL_ID_HERE" },
        emojis: { enabled: false, name: "🎨︱Emojis: {counter}", channel: "CHANNEL_ID_HERE" },
        bans: { enabled: false, name: "🔨︱Bans: {counter}", channel: "CHANNEL_ID_HERE" },
        invites: { enabled: false, name: "📨︱Invites: {counter}", channel: "CHANNEL_ID_HERE" }
    }
}

module.exports = config
```

> Replace all `ROLE_ID_HERE`, `CHANNEL_ID_HERE`, and `CATEGORY_ID_X` with your actual Discord IDs.

---

## ▶️ Running the Bot

Start the bot with:

```bash
node .
```

The bot will automatically update stats in the channels you configured.

---

## 📂 Project Structure

```
/commands
/events
/systems
config.js
index.js
.env
README.md
```

---

## 📝 License

This project is provided as-is. You may modify it for private or community use.

---

## ❤️ Credits

Created by **Finn**
Configuration guidance and English README by ChatGPT
