---
title: Setup Guide Chatgpt
deprecated: false
hidden: true
metadata:
  robots: index
---
Install in Chatgpt Codex

ChatGPT (Codex) uses a Personal Access Token (PAT) for authentication rather than OAuth, so there’s one extra step compared to Claude Desktop. It only takes a minute.

Step 1: Generate a Personal Access Token
Log in to the Lifesight platform.
Navigate to the token generation URL and select your workspace.

[https://console.lifesight.io/account/codex-tokens](https://console.lifesight.io/account/codex-tokens)

<br />

Name your token (e.g. Codex or your project name) and click Generate.

<br />

Copy the generated key straight away, it won’t be shown again.

If you belong to multiple workspaces, generate a separate token for each one.

Step 2: Add the MCP Server in ChatGPT Codex
Go to Codex  →Settings

<br />

Then go to MCP Server → Add server.

<br />

Fill in:
Server name: Any label, e.g. Lifesight
HTTP URL

[https://mcp.lifesight.io/mcp](https://mcp.lifesight.io/mcp)

<br />

Authorization key: Enter Authorization as the key name, and prefix your token with Bearer as the value.

Click Save to finalize the connection.
Open a new chat and select the Lifesight MCP server to begin querying your models.

You’re connected! Start a new chat with the Lifesight MCP server selected and ask anything. Here are some good first questions to try:

“What’s my \[Quarter] budget allocation by channel?”
“Which channel drove the highest iROAS last week?”
“I have \[ $200K] to reallocate, where should it go to maximize revenue?”
“Show me how \[Ad Channel 1]  has been performing compared to  \[Ad Channel 2] over the last \[N days].”
