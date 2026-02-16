# Clawdbot (now OpenClaw) 🤖

![Clawdbot Logo](logo.png)

> **Privacy-First, Self-Hosted AI Assistant.**

Clawdbot is an open-source AI companion that lives on your hardware. It integrates with WhatsApp, Telegram, iMessage, and Discord to automate tasks and manage data without ever sending logs to the cloud.

---

## ✨ Highlights

- 🏠 **Local & Private**: Your data never leaves your machine.
- 💬 **Omnichannel**: Chat via WhatsApp, Telegram, or iMessage.
- 🚀 **Automation**: Runs browser scripts and CLI tools locally.
- 🧠 **Memory**: Persistent context and local vector storage.
- 🔌 **Extensible**: Add custom JS/Python "skills" easily.

---

## 🚀 Quick Start

### 1. Setup

```bash
git clone https://github.com/your-repo/clawdbot.git && cd clawdbot
npm install
```

### 2. Configure (`.env`)

```env
AI_PROVIDER=anthropic
ANTHROPIC_API_KEY=your_key
PLATFORM=telegram
TELEGRAM_BOT_TOKEN=your_token
```

### 3. Run

```bash
npm start
```

---

## 🛠️ Dev: Create a Skill

Add a file to `skills/` to give Clawdbot new powers:

```javascript
export const statusSkill = {
  name: "get_status",
  description: "Check system health",
  execute: async () => "System is optimal. 🚀",
};
```

---

## 🔒 Safety

Run Clawdbot in a container or VM. It has broad system access—audit the code and restrict network permissions accordingly.

---

Built with ❤️ by the Clawdbot Community.
