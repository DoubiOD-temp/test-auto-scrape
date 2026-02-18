# Clawdbot (now OpenClaw) 🤖

> **Your Open-Source, Self-Hosted Personal AI Assistant.**

**Clawdbot** is a powerful, privacy-first AI companion designed to live on your own hardware. It integrates seamlessly with your favorite messaging platforms—WhatsApp, Telegram, iMessage, Slack, and Discord—to automate your life, manage your data, and provide intelligent insights without ever sending your personal logs to the cloud.

## 🛠️ Technology Stack

Clawdbot is built to be flexible and powerful:

- **AI Engine**: Supports Claude 3.5 Sonnet, GPT-4o, and local models via Ollama.
- **Backend**: High-performance engine designed for low latency and high reliability.
- **Connectivity**: Native integrations with iMessage, WhatsApp (via Multi-Device API), and Telegram.

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

## 🔒 Security & Privacy

Clawdbot is designed with a **"security by default"** architecture. Because it requires access to sensitive data (messages, calendar, etc.), we strongly recommend:

- Running it inside a dedicated container or VM.
- Restricting network access to only necessary APIs.
- Regularly auditing the open-source code for updates.

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

Built with ❤️ by the Clawdbot Community.
