# DoubleX Plugin for Claude Code

Manage your [DoubleX](https://app.doublex.ai) AI agents and multi-agent flows directly from Claude Code — no need to open the web panel.

This plugin connects Claude Code to the DoubleX platform via a remote MCP server, exposing 13 tools for creating, editing, running, and chatting with agents and flows.

---

## Prerequisites

- [Claude Code](https://claude.ai/code) installed
- A DoubleX account with an API key (`dxp_...`) — generate one at **app.doublex.ai → Settings → API Keys**

---

## Installation

### Step 1 — Register the MCP server

Add the DoubleX MCP server to Claude Code by running:

```bash
claude mcp add --transport http doublex https://agent.doublex.ai/mcp
```

Or manually add the following to your `~/.claude/settings.json` under `mcpServers`:

```json
{
  "mcpServers": {
    "doublex": {
      "type": "http",
      "url": "https://agent.doublex.ai/mcp",
      "headers": {
        "Authorization": "Bearer ${DOUBLEX_API_KEY}"
      }
    }
  }
}
```

### Step 2 — Install the skill commands

Copy the `commands/doublex/` folder into your project's `.claude/commands/` directory:

```bash
cp -r commands/doublex .claude/commands/doublex
```

> The `.claude/commands/` folder should be at the root of your project. Create it if it doesn't exist.

### Step 3 — Configure your API key

Open Claude Code and run:

```
/doublex:setup
```

Follow the instructions to paste your API key. It will be stored in your shell profile as `DOUBLEX_API_KEY` and picked up automatically on every session.

---

## Available Commands

| Command | Description |
|---|---|
| `/doublex:ajuda` | Show all available commands |
| `/doublex:setup` | Configure your API key |
| `/doublex:meus-agentes` | List all your AI agents |
| `/doublex:novo-agente` | Create a new AI agent |
| `/doublex:detalhe-agente` | View full details of an agent |
| `/doublex:editar-agente` | Edit an existing agent |
| `/doublex:conversar` | Chat directly with an agent |
| `/doublex:meus-flows` | List all your multi-agent flows |
| `/doublex:novo-flow` | Create a new multi-agent flow |
| `/doublex:detalhe-flow` | View flow structure and nodes |
| `/doublex:editar-flow` | Edit a flow's graph (nodes and edges) |
| `/doublex:executar-flow` | Send a message to a flow and wait for the response |
| `/doublex:status-flow` | Run a flow in background and track its status |
| `/doublex:modelos` | List all available AI models by provider |

---

## How It Works

```
Claude Code
    ↓  /doublex:* skill
    ↓  calls MCP tool (list_agents, create_agent, run_flow...)
    ↓  HTTP POST https://agent.doublex.ai/mcp
DoubleX Backend
    ↓  authenticates via API key
    ↓  executes and returns result
Claude Code displays the result
```

Each skill file (`.md`) instructs Claude on what to ask the user and which MCP tools to call in sequence. The MCP server is hosted by DoubleX — no local server required.

---

## Authentication

All requests are authenticated using your DoubleX API key via the `Authorization: Bearer dxp_...` header. The key is read from the `DOUBLEX_API_KEY` environment variable set during `/doublex:setup`.

To generate or revoke keys: **app.doublex.ai → Settings → API Keys**
