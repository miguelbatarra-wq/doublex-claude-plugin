# DoubleX Plugin for Claude Code

Manage your [DoubleX](https://app.doublex.ai) AI agents and multi-agent flows directly from Claude Code — no need to open the web panel.

This plugin connects Claude Code to the DoubleX platform via a remote MCP server, exposing 13 tools for creating, editing, running, and chatting with agents and flows.

---

## Prerequisites

- [Claude Code](https://claude.ai/code) installed
- A DoubleX account with an API key (`dxp_...`) — generate one at **app.doublex.ai → Settings → API Keys**

---

## Installation

Inside Claude Code, run:

```
/plugin install miguelbatarra-wq/doublex-claude-plugin
```

This automatically registers the MCP server and installs all commands.

Then configure your API key:

```
/doublex:setup
```

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
    ↓  /doublex:* command
    ↓  calls MCP tool (list_agents, create_agent, run_flow...)
    ↓  HTTP POST https://agent.doublex.ai/mcp
DoubleX Backend
    ↓  authenticates via API key
    ↓  executes and returns result
Claude Code displays the result
```

The MCP server is hosted by DoubleX — no local server required.

---

## Authentication

All requests use `Authorization: Bearer dxp_...` read from the `DOUBLEX_API_KEY` environment variable set during `/doublex:setup`.

Generate or revoke keys at **app.doublex.ai → Settings → API Keys**.
