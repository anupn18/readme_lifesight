---
title: MCP
hidden: true
---
The Lifesight Model Context Protocol (MCP) server enables AI-powered code editors like Cursor and Windsurf, plus general-purpose tools like Claude Desktop, to interact directly with your Lifesight API and documentation.

## What is MCP?

Model Context Protocol (MCP) is an open standard that allows AI applications to securely access external data sources and tools. The Lifesight MCP server provides AI agents with:

* **Direct API access** to Lifesight functionality
* **Documentation search** capabilities
* **Real-time data** from your Lifesight account
* **Code generation** assistance for Lifesight integrations

## Lifesight MCP Server Setup

Lifesight hosts a remote MCP server at `https://docs.lifesight.io/mcp`. Configure your AI development tools to connect to this server. If your APIs require authentication, you can pass in headers via query parameters or however headers are configured in your MCP client.

<Tabs>
  <Tab title="Cursor">
    **Add to `~/.cursor/mcp.json`:**

    ```json
    {
      "mcpServers": {
        "lifesight": {
          "url": "https://docs.lifesight.io/mcp"
        }
      }
    }
    ```

    </Tab>
  <Tab title="Windsurf">
    **Add to `~/.codeium/windsurf/mcp_config.json`:**

    ```json
    {
      "mcpServers": {
        "lifesight": {
          "url": "https://docs.lifesight.io/mcp"
        }
      }
    }
    ```

  </Tab>
  <Tab title="Claude Desktop">
    **Add to `claude_desktop_config.json`:**

    ```json
    {
      "mcpServers": {
        "lifesight": {
          "url": "https://docs.lifesight.io/mcp"
        }
      }
    }
    ```

  </Tab>
</Tabs>

## Testing Your MCP Setup

Once configured, you can test your MCP server connection:

1. **Open your AI editor** (Cursor, Windsurf, etc.)
2. **Start a new chat** with the AI assistant
3. **Ask about Lifesight** - try questions like:
   * "How do I [common use case]?"
   * "Show me an example of [API functionality]"
   * "Create a [integration type] using Lifesight"

The AI should now have access to your Lifesight account data and documentation through the MCP server.