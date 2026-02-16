# Clawdbot (now OpenClaw) 🤖

![Clawdbot Logo](logo.png)

> **Privacy-First, Self-Hosted AI Assistant.**

**Clawdbot** is an open-source AI companion that runs on your local machine. It bridges your favorite messaging apps (WhatsApp, Telegram, iMessage, Discord) with your file system and local tools, allowing you to automate tasks without compromising privacy.

---

## ✨ Features

- **🏠 Privacy First**: Your data stays on your device. Support for local LLMs (Ollama/Llama 3).
- **💬 Omnichannel**: Chat via Telegram, WhatsApp, iMessage, or Discord.
- **🚀 Automation**: Execute shell commands, browse the web, and control smart home devices.
- **🧠 Memory**: Persistent vector storage remembers context across conversations.
- **🔌 Extensible**: Add new capabilities with simple JavaScript/Python plugins.

---

## 🚀 Quick Start

### 1. Install

```bash
git clone https://github.com/your-repo/clawdbot.git
cd clawdbot
npm install
```

### 2. Configure

Copy `.env.example` to `.env` and set your keys:

```env
AI_PROVIDER=anthropic      # or 'ollama' for local
ANTHROPIC_API_KEY=sk-...   # if using cloud
PLATFORM=telegram          # whatsapp, imessage, discord
TELEGRAM_BOT_TOKEN=...
```

### 3. Run

```bash
npm start
```

---

## 🛠️ Create a Skill

Extend functionality by adding a file to `skills/`.

**Example: `skills/roll_dice.js`**

```javascript
export const diceSkill = {
  name: "roll_dice",
  description: "Roll a die",
  execute: async () => `🎲 You rolled a ${Math.floor(Math.random() * 6) + 1}!`,
};
```

---

## 🔒 Security

Clawdbot has system access. **Always audit new skills** and consider running in a Docker container for isolation.

---

Distributed under the **MIT License**.
