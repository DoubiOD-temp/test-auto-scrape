# Clawdbot (now OpenClaw) 🤖

![Clawdbot Logo](logo.png)

> **The Privacy-First, Self-Hosted AI Assistant that lives on your machine.**

**Clawdbot** is a fully open-source AI companion designed for power users who want the convenience of an intelligent assistant without sacrificing privacy. Unlike cloud-based alternatives that harvest your data, Clawdbot runs entirely on your own hardware (Mac, Windows, Linux, or VPS).

It serves as a bridge between your favorite messaging apps—WhatsApp, Telegram, iMessage, Discord—and your local system, allowing you to automate tasks, manage files, and execute complex workflows through simple natural language.

---

## 🌟 Why Clawdbot?

We built Clawdbot because we believe your AI should work for _you_, not a corporation.

1.  **Total Privacy**: Your conversations, calendar data, and files never leave your machine unless you explicitly tell them to. Use local models like Llama 3 for 100% offline privacy.
2.  **Context Aware**: Clawdbot remembers your preferences, past conversations, and specific project details over weeks and months using local vector storage.
3.  **Real-World Action**: Most chatbots just talk. Clawdbot _does_. It can browse the web, write files, control your smart home, and run local scripts.

---

## ✨ Key Capabilities

- **🏠 Private & Local**: Self-hosted architecture ensures no data leakage.
- **💬 Omnichannel Support**: Talk to your assistant where you already are:
  - **Telegram**: Rich media support, voice notes, and location sharing.
  - **WhatsApp**: Seamless integration via Multi-Device API.
  - **iMessage**: Native Mac integration for blue-bubble commands.
  - **Discord**: Perfect for server management and community automation.
- **🚀 Powerful Automation**:
  - **Headless Browsing**: "Go check the price of X on Amazon and let me know if it drops."
  - **System Control**: "Turn on my focus mode" or "Run the backup script."
- **🧠 Persistent Memory**: Uses RAG (Retrieval-Augmented Generation) to recall details from previous chats.
- **🔌 Extensible Skill System**: Drop a simple JavaScript or Python file into a folder to teach Clawdbot new tricks instantly.

---

## 🏗️ Architecture

Clawdbot follows a modular "Brain & Limbs" architecture:

- **The Brain**: The core logic engine that processes intent. It can be powered by cloud APIs (Anthropic Claude 3.5, OpenAI GPT-4o) or local models (Ollama/Llama 3).
- **The Limbs (Adapters)**: Lightweight connectors that translate protocols from Telegram, WhatsApp, etc., into a unified internal format.
- **The Hands (Tools)**: A secure execution sandbox where "Skills" are run. This is where browsing, file manipulation, and script execution happen.

---

## 🚀 Getting Started

### Prerequisites

- Node.js v18 or higher
- (Optional) Docker for sandboxing
- (Optional) Ollama for local model inference

### 1. Installation

Clone the repository and install the dependencies:

```bash
git clone https://github.com/your-repo/clawdbot.git
cd clawdbot
npm install
```

### 2. Configuration

Copy the example environment file and configure your keys:

```bash
cp .env.example .env
nano .env
```

**Essential `.env` Configuration:**

| Variable             | Description                                          | Example        |
| :------------------- | :--------------------------------------------------- | :------------- |
| `AI_PROVIDER`        | The brain provider (`anthropic`, `openai`, `ollama`) | `anthropic`    |
| `ANTHROPIC_API_KEY`  | Your API key (if using cloud)                        | `sk-ant...`    |
| `PLATFORM`           | The primary messaging platform to listen on          | `telegram`     |
| `TELEGRAM_BOT_TOKEN` | Token from @BotFather (if using Telegram)            | `12345:ABC...` |
| `ALLOWED_USERS`      | Comma-separated list of user IDs allowed to chat     | `user1,user2`  |

### 3. Launching

Start the bot in development mode:

```bash
npm run dev
```

Or for production usage:

```bash
npm start
```

---

## 🛠️ Extending Clawdbot: Creating Skills

Clawdbot's true power lies in its extensibility. You can add new capabilities by simply creating a file in the `skills/` directory.

**Example: A Currency Converter Skill**

Create `skills/currency.js`:

```javascript
export const currencySkill = {
  name: "convert_currency",
  description: "Converts an amount from one currency to another",
  parameters: {
    type: "object",
    properties: {
      amount: { type: "number", description: "The amount of money" },
      from: {
        type: "string",
        description: "Currency code to convert from (e.g. USD)",
      },
      to: {
        type: "string",
        description: "Currency code to convert to (e.g. EUR)",
      },
    },
    required: ["amount", "from", "to"],
  },
  execute: async ({ amount, from, to }) => {
    // In a real skill, you would fetch real rates
    const rate = 0.92;
    const result = amount * rate;
    return `${amount} ${from} is approximately ${result.toFixed(2)} ${to}.`;
  },
};
```

Clawdbot will automatically detect this file, register the tool with the LLM, and you can immediately ask: _"Hey, how much is $50 in Euros?"_

---

## 🗺️ Roadmap

- [ ] **v1.1**: Native Vision support (analyze images sent via chat).
- [ ] **v1.2**: Voice Mode (speech-to-text and text-to-speech for voice notes).
- [ ] **v1.5**: "Ghost Mode" - One-click setup for fully offline (Ollama + local vector DB) operation.
- [ ] **v2.0**: Multi-agent support (swarm capabilities for complex tasks).

---

## 🔒 Security & Best Practices

Clawdbot is a powerful tool with access to your system.

1.  **Sandboxing**: We strongly recommend running Clawdbot in a Docker container or VM to isolate it from your main host system.
2.  **Audit Skills**: Only install skills from trusted sources.
3.  **Network**: Limit outbound traffic to only essential APIs.

---

## 🤝 Contributing

We welcome contributions! Whether it's a new skill, a bug fix, or a documentation improvement, please feel free to open a Pull Request.

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

Built with ❤️ by the Clawdbot Community.
