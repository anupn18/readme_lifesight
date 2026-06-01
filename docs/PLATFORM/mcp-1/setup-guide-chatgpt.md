---
title: Setup Guide Chatgpt
excerpt: Connect Lifesight MCP to Chatgpt Codex in 2 minutes.
deprecated: false
hidden: true
metadata:
  robots: index
---
## **Before You Start**

Ensure you have the following before proceeding:

1. An active Lifesight workspace. If you're evaluating Lifesight, book a demo and ask for a sandbox.
2. Claude Desktop (latest version)
3. Lifesight MCP URL: [https://mcp.lifesight.io/mcp/](https://mcp.lifesight.io/mcp)



***

## Install in Chatgpt Codex

ChatGPT (Codex) uses a Personal Access Token (PAT) for authentication rather than OAuth, so there’s one extra step compared to Claude Desktop. It only takes a minute.

1. **Generate a Personal Access Token**
   - Log in to the Lifesight platform.
   - Navigate to the token generation URL and select your workspace.

> 📌 Token generation URL
>
> &#x20;<Anchor target="_blank" href="https://console.lifesight.io/account/codex-tokens">https://console.lifesight.io/account/codex-tokens</Anchor>

- &#x20;Name your token (e.g. Codex or your project name) and click Generate.
- Copy the generated key straight away, it won’t be shown again.
- If you belong to multiple workspaces, generate a separate token for each one.

2. **Add the MCP Server in ChatGPT Codex**
   - Go to Codex  →Settings
   - Then go to MCP Server → Add server.
   - Fill in:<br />Server name: Any label, e.g. Lifesight<br />HTTP URL

> 📌 HTTP URL
>
> [https://mcp.lifesight.io/mcp](https://mcp.lifesight.io/mcp "https://mcp.lifesight.io/mcp")

- Authorization key: Enter Authorization as the key name, and prefix your token with Bearer as the value.
- Click Save to finalize the connection.
- Open a new chat and select the Lifesight MCP server to begin querying your models.

You’re connected! Start a new chat with the Lifesight MCP server selected and ask anything.&#x20;

Here are some good first questions to try:

<Cards>
  <Card title="Getting Started" href="#" icon="fa-rocket">
    New to our platform? Follow this guide to get started.
  </Card>

  <Card title="API Reference" href="#" icon="fa-code">
    Explore our interactive API reference.
  </Card>

  <Card title="Support & Community" href="#" icon="fa-comments" target="_blank">
    Join our community or checkout our FAQ.
  </Card>
</Cards>

**_“What’s my \[Quarter] budget allocation by channel?”<br />“Which channel drove the highest iROAS last week?”<br />“I have \[ $200K] to reallocate, where should it go to maximize revenue?”<br />“Show me how \[Ad Channel 1]  has been performing compared to  \[Ad Channel 2] over the last \[N days].”<br />_**

***

## **Verify Your Setup**

These three prompts work in both Claude Desktop and ChatGPT. If you get structured output from your account, you’re good to go.

| Prompt                                                    | Expected Outcome                                              |
| --------------------------------------------------------- | ------------------------------------------------------------- |
| _List every causal model in my workspace._                | Markdown table: model names, last-run date, confidence range. |
| _What was my best-performing channel last week by iROAS?_ | Ranked answer with methodology footnote.                      |
| _Find the methodology document for geo-lift testing._     | Doc summary with link back to Lifesight.                      |

<br />
