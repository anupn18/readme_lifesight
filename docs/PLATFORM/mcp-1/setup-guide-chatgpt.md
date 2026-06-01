---
title: Setup Guide Chatgpt
excerpt: Connect Lifesight MCP to Chatgpt Codex in 2 minutes.
deprecated: false
hidden: false
metadata:
  robots: index
next:
  pages:
    - slug: prompt-library
      title: Prompt Library
      type: basic
---
## **Before You Start**

Ensure you have the following before proceeding:

1. An active Lifesight workspace. If you're evaluating Lifesight, book a demo and ask for a sandbox.
2. ChatGPT with Custom Connectors enabled (Team, Enterprise, or Plus)
3. Lifesight MCP URL: [https://mcp.lifesight.io/mcp/](https://mcp.lifesight.io/mcp)

<br />

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


<Image src="https://files.readme.io/af93c6fc759dbc01850666585b43491ebdddcad6bcdad45a5848790f40bd6187-Screenshot_2026-06-01_at_10.23.46_PM.png" align="center" width="500px" border={true} />


- Copy the generated token straight away, it won’t be shown again.
- If you belong to multiple workspaces, generate a separate token for each one.

2. **Add the MCP Server in ChatGPT Codex**
   - Go to Codex  →Settings
   - Then go to MCP Server → Add server → Streamable HTTP
   - Fill in: Server name: Any label, e.g. Lifesight
   - Fill in Bearer Token MCP\_BEARER\_TOKEN

     <Image src="https://files.readme.io/83a5cf2fac4e344a6148eb2be1db33d467031f820a0d4921c0892830e77c40ed-Screenshot_2026-06-01_at_10.16.26_PM.png" align="left" width="500px" border={true} />


   -

> 📌 HTTP URL
>
> [https://mcp.lifesight.io/mcp](https://mcp.lifesight.io/mcp "https://mcp.lifesight.io/mcp")

- Authorization key: Enter Authorization as the key name, and add your token copied from the Lifesight earlier.&#x20;
- Click Save to finalize the connection.
- Open a new chat and select the Lifesight MCP server to begin querying your models.

You’re connected! Start a new chat with the Lifesight MCP server selected and ask anything.&#x20;

| **Here are some good first questions to try:**                                                                                                                                                                                                                                                                  |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| "**_What’s my \[Quarter] budget allocation by channel?”<br />“Which channel drove the highest iROAS last week?”<br />“I have \[ $200K] to reallocate, where should it go to maximize revenue?”<br />“Show me how \[Ad Channel 1]  has been performing compared to  \[Ad Channel 2] over the last \[N days].”_** |

***

## **Verify Your Setup**

These three prompts work in both Claude Desktop and ChatGPT. If you get structured output from your account, you’re good to go.

| Prompt                                                    | Expected Outcome                                              |
| --------------------------------------------------------- | ------------------------------------------------------------- |
| _List every causal model in my workspace._                | Markdown table: model names, last-run date, confidence range. |
| _What was my best-performing channel last week by iROAS?_ | Ranked answer with methodology footnote.                      |
| _Find the methodology document for geo-lift testing._     | Doc summary with link back to Lifesight.                      |

<br />