# Clawdbot (now OpenClaw) 🤖

![Clawdbot Logo](logo.png)

> **Your Open-Source, Self-Hosted Personal AI Assistant.**

**Clawdbot** is a powerful, privacy-first AI companion designed to live on your own hardware. It integrates seamlessly with your favorite messaging platforms—WhatsApp, Telegram, iMessage, Slack, and Discord—to automate your life, manage your data, and provide intelligent insights without ever sending your personal logs to the cloud.

---

## ✨ Key Features

- 🏠 **Privacy-First & Self-Hosted**: Run Clawdbot on your Mac, Windows, Linux, or VPS. Your data stays where it belongs: with you.
- 💬 **Multi-Platform Integration**: Interact with your AI assistant directly through the apps you already use every day. Supports WhatsApp, Telegram, iMessage, and Discord.
- 🚀 **Advanced Task Automation**: Beyond simple chat, Clawdbot can execute complex browser automations, control smart home devices, and run custom scripts on your machine.
- 🧠 **Persistent Memory**: Clawdbot remembers your preferences, past conversations, and specific instructions, evolving as you interact with it.
- 🔔 **Proactive Intelligence**: Get morning briefings, custom alerts, and proactive suggestions based on your schedule and interests.
- 🔌 **Extensible Plugin System**: Open-source and highly customizable. Add new "skills" or integrate with local AI models like Ollama for 100% offline operation.

---

## 🏗️ System Architecture

Clawdbot is designed with a modular "Brain & Limbs" architecture:

- **The Brain (Core Orchestrer)**: Handles LLM reasoning, state management, and memory retrieval. It uses a vector database (Chromadb/Pinecone) to maintain context over months of interaction.
- **The Messaging Layer**: A unified adapter system that translates incoming messages from WhatsApp, iMessage, or Slack into a standardized format for the Brain.
- **The Skill Engine**: A sandboxed environment where Javascript or Python scripts (Plugins) are executed to perform real-world actions like scraping a URL or sending an email.
- **The Toolset**: Native integration with Playwright for browser automation and local CLI tools.

---

## 🛠️ Technology Stack

Clawdbot is built to be flexible and powerful:

- **AI Engine**: Supports Claude 3.5 Sonnet, GPT-4o, and local models via Ollama.
- **Backend**: Node.js / TypeScript for speed and massive library support.
- **Memory**: Vector-based RAG (Retrieval-Augmented Generation) for long-term memory.
- **Connectivity**: Native integrations with iMessage, WhatsApp (via Multi-Device API), and Telegram.

---

## 🌟 Example Use Cases

| **Workflow**          | **How it works**                                                                                                              |
| :-------------------- | :---------------------------------------------------------------------------------------------------------------------------- |
| **Daily Briefing**    | Clawdbot scrapes your favorite news sites at 7 AM and sends a summary to your WhatsApp.                                       |
| **Meeting Assistant** | Forward a calendar invite to Clawdbot; it will research the attendees and provide a "cheat sheet" before the call.            |
| **Smart Researcher**  | Ask "Find me the best price for an RTX 4090 on Amazon." Clawdbot opens a headless browser, compares prices, and reports back. |
| **Personal PA**       | "Hey Clawdbot, remind me to buy milk when I'm near a grocery store." Uses GPS integration (via Telegram) to trigger alerts.   |

---

## 🚀 Getting Started

### 1. Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/your-repo/clawdbot.git
cd clawdbot
npm install
```

### 2. Configuration

Create a `.env` file and add your API keys and configuration settings:

```env
AI_PROVIDER=anthropic
ANTHROPIC_API_KEY=your_key_here
PLATFORM=telegram
TELEGRAM_BOT_TOKEN=your_token_here
```

### 3. Run Locally

```bash
npm start
```

---

## 🛠️ Developing Skills

You can easily extend Clawdbot by adding new functions to the `skills/` directory.

### Example: A Simple Weather Skill

```javascript
// skills/weather.js
export const weatherSkill = {
  name: "get_weather",
  description: "Gets the current weather for a location",
  execute: async (location) => {
    const data = await fetch(`https://api.weather.com/...&q=${location}`);
    return `The weather in ${location} is currently sunny.`;
  },
};
```

Clawdbot automatically detects new skills and makes them available to the AI via **Function Calling**.

---

## 🔒 Security & Privacy

Clawdbot is designed with a **"security by default"** architecture. Because it requires access to sensitive data (messages, calendar, etc.), we strongly recommend:

- Running it inside a dedicated container or VM.
- Restricting network access to only necessary APIs.
- Regularly auditing the open-source code for updates.

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 🗺️ Roadmap

- [ ] **v1.2**: Native vision support (send an image to Clawdbot via WhatsApp for analysis).
- [ ] **v1.5**: "Ghost Mode" - Fully offline operation using Llama 3 on local hardware.
- [ ] **v2.0**: Peer-to-peer encrypted sync between multiple Clawdbot instances.
- [ ] **v2.1**: Voice integration for hands-free control via Siri/Google Assistant hooks.

---

Built with ❤️ by the Clawdbot Community.
