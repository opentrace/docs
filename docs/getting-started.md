# Getting Started

## What is OpenTrace?

OpenTrace gives your AI assistant deep knowledge about your system architecture. It understands your services, how they connect, and how they depend on each other. This means you can ask questions about your system and get accurate, contextual answers.

## Setup

To connect OpenTrace to your AI assistant, add the following to your MCP configuration:

```json
{
  "mcpServers": {
    "opentrace": {
      "type": "http",
      "url": "https://api.opentrace.ai/mcp/v1",
      "headers": {
        "Authorization": "Bearer YOUR_API_TOKEN"
      }
    }
  }
}
```

Replace `YOUR_API_TOKEN` with your OpenTrace API token from the dashboard.

## Try It Out

Once connected, try asking your AI assistant these questions:

**Explore your system:**

> "What services are in my system?"

> "Tell me about the authentication service"

**Understand dependencies:**

> "What does the order service depend on?"

> "What services would be affected if the database goes down?"

**Investigate issues:**

> "Help me understand how requests flow from the API to the database"

> "What's the connection path between the frontend and the payment service?"

Your AI assistant now has the context it needs to give you meaningful answers about your architecture.

## Next Steps

- [What You Can Do](capabilities.md) - Full list of questions you can ask
- [Example Workflows](workflows.md) - Common scenarios and how to approach them
