# Claude CLI (Claude Code) 🤖 terminal-based agentic coder

> **Build software at the speed of thought, directly from your terminal.**

**Claude Code** is an agentic coding tool by Anthropic that lives where you work: the command line. It isn't just an autocomplete engine; it's a full-fledged collaborator that can understand your entire codebase, execute terminal commands, edit files, and manage your Git workflow—all through natural language.

---

## � Quick Start

### 1. Prerequisites

Ensure you have the following installed:

- **Node.js**: v18.0.0 or later.
- **Anthropic API Key**: A valid key with access to Claude 3.5 Sonnet.

### 2. Installation

Install the Claude CLI globally using npm:

```bash
npm install -g @anthropic-ai/claude-code
```

### 3. Verification

Run the version check to ensure it's installed correctly:

```bash
claude --version
```

---

## ⌨️ Common Commands

| Command         | Description                                             |
| :-------------- | :------------------------------------------------------ |
| `claude`        | Start an interactive session in the current directory.  |
| `claude "task"` | Run a one-off task (e.g., `claude "fix the login bug"`) |
| `claude login`  | Authenticate with your Anthropic account.               |
| `claude config` | Manage your preferences and model settings.             |

---

## �️ Performance & Capabilities

Claude CLI is designed for deep integration with your development environment:

- **Context-Aware:** Automatically indexes your local files to answer complex questions about your architecture.
- **Safe Execution:** Can run tests, build scripts, and linting commands to verify its own work.
- **Git Mastery:** Can stage changes, write meaningful commit messages, and even help with PR descriptions.
- **Zero Latency:** Optimized for the terminal, providing a fast, text-based interface that doesn't break your flow.

---

## 💡 Example Workflows

### Bug Hunting

`> claude "Investigate why the /api/user endpoint is returning a 500 error and fix it."`
Claude will read the logs, find the file, identify the logic error, and offer to apply a fix.

### Modernization

`> claude "Refactor all Class components in /src/components to Functional components with Hooks."`
Claude will systematically update your files while keeping the logic intact.

### Testing

`> claude "Write Jest unit tests for the utility functions in utils/math.ts and run them to make sure they pass."`
Claude will write the tests AND execute them in your terminal.

---

## 📜 Official Resources

- [Technical Documentation](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code)
- [Anthropic Console](https://console.anthropic.com/)
- [Feedback & Support](https://support.anthropic.com)

---

Built for developers who live in the terminal. ⚡
