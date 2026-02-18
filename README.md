# Claude CLI (Claude Code) 🤖 Terminal-Based Agentic Coder

> **Build software at the speed of thought, directly from your terminal.**

**Claude Code** is an agentic coding tool by Anthropic that lives where you work: the command line. It isn't just an autocomplete engine; it's a full-fledged collaborator that can understand your entire codebase, execute terminal commands, edit files, and manage your Git workflow—all through natural language.

---

## 🚀 Quick Start

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

## ⌨️ Common Commands & REPL Usage

| Command / Shortcut | Description                                             |
| :----------------- | :------------------------------------------------------ |
| `claude`           | Start an interactive session in the current directory.  |
| `claude "task"`    | Run a one-off task (e.g., `claude "fix the login bug"`) |
| `claude login`     | Authenticate with your Anthropic account.               |
| `/config`          | Access the interactive configuration menu (REPL only).  |
| `/permissions`     | View and manage tool execution permissions.             |
| `!command`         | Execute a shell command directly from the REPL.         |
| `@filename`        | Reference a specific file context in your message.      |

---

## 🛠️ Performance & Capabilities

Claude CLI is designed for deep integration with your development environment:

- **Agentic Reasoning:** Unlike simple chat windows, Claude Code uses "Extended Thinking" to reason through complex architectural problems before writing a single line of code.
- **Context-Aware:** Automatically indexes your local files and respects your `.gitignore`.
- **Safe Execution:** Can run tests, build scripts, and linting commands to verify its own work.
- **Git Mastery:** Can stage changes, write meaningful commit messages, and even help with PR descriptions.
- **Subagents:** For massive tasks, Claude can spawn sub-agents to parallelize work across different parts of your system.

---

## 🔒 Security & Workflow Modes

Claude Code prioritizes safety with a tiered permission system:

### Permission Modes

- **Default:** Claude asks for permission before executing potentially sensitive commands.
- **Plan Mode:** Claude analyzes and proposes changes without modifying any files.
- **Auto-Accept:** Streamlines the workflow for low-risk changes (use with caution).

### Safety Features

- **Checkpoints:** Every file edit is reversible. You can rollback changes if the result isn't what you expected.
- **Sandboxing:** Write operations are strictly limited to your project's working directory.
- **Human-in-the-loop:** You review every diff before it is committed to your file system.

---

## ⚙️ Configuration & Customization

Claude Code is highly configurable through a hierarchical settings system:

1.  **Project Context (`CLAUDE.md`):** Create a `CLAUDE.md` in your project root to provide project-specific conventions, tech stack details, and coding standards.
2.  **User Settings:** Managed in `~/.claude/settings.json`.
3.  **Local Overrides:** Managed in `.claude/settings.local.json`.

### MCP Integration

Claude Code supports the **Model Context Protocol (MCP)**, allowing it to connect to external tools like:

- **Jira/GitHub Issues:** For tracking progress.
- **Sentry:** For analyzing production errors.
- **Custom Databases:** For querying schemas directly.

---

## 💡 Example Workflows

### Bug Hunting

`> claude "Investigate why the /api/user endpoint is returning a 500 error and fix it."`
Claude will read the logs, find the file, identify the logic error, and offer to apply a fix.

### Modernization

`> claude "Refactor all Class components in /src/components to Functional components with Hooks."`
Claude will systematically update your files while keeping the logic intact.

### Testing & Quality

`> claude "Write Jest unit tests for the utility functions in utils/math.ts and run them to make sure they pass."`
Claude will write the tests AND execute them in your terminal to verify correctness.

---

## 📜 Official Resources

- [Technical Documentation](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code)
- [Anthropic Console](https://console.anthropic.com/)
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io)

---

Built for developers who live in the terminal. ⚡
