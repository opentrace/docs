# Claude Code

Connect OpenTrace to Claude Code to give your AI assistant deep knowledge about your system architecture.

## What is Claude Code?

Claude Code is Anthropic's official command-line interface for Claude. It enables Claude to understand your codebase, execute commands, and assist with software engineering tasks directly from your terminal.

By connecting OpenTrace to Claude Code, you give Claude access to your system's architecture, service dependencies, and runtime relationships - enabling it to answer questions about your infrastructure and help debug issues.

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and configured
- An OpenTrace account with an API token

## Setup Steps

--8<-- "get-api-token.md"

### 2. Configure MCP

Claude Code uses MCP (Model Context Protocol) configuration files to connect to external services. You can configure OpenTrace at the project level or globally.

#### Option A: Project-Level Configuration (Recommended)

Create a `.mcp.json` file in your project root:

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

Replace `YOUR_API_TOKEN` with your OpenTrace API token.

!!! tip
    Use an environment variable to avoid committing your token:
    ```json
    {
      "mcpServers": {
        "opentrace": {
          "type": "http",
          "url": "https://api.opentrace.ai/mcp/v1",
          "headers": {
            "Authorization": "Bearer ${OPENTRACE_API_TOKEN}"
          }
        }
      }
    }
    ```
    Then set the environment variable: `export OPENTRACE_API_TOKEN=your_token_here`

#### Option B: Global Configuration

To make OpenTrace available in all your Claude Code sessions, add the configuration to your global settings file.

**macOS / Linux:**

Edit `~/.claude/settings.json`:

```json
{
  "mcpServers": {
    "opentrace": {
      "type": "http",
      "url": "https://api.opentrace.ai/mcp/v1",
      "headers": {
        "Authorization": "Bearer ${OPENTRACE_API_TOKEN}"
      }
    }
  }
}
```

**Windows:**

Edit `%USERPROFILE%\.claude\settings.json` with the same configuration.

### 3. Verify the Connection

Start Claude Code in your terminal:

```bash
claude
```

Ask Claude to verify the connection:

> "What services are available in OpenTrace?"

If configured correctly, Claude will be able to query your system architecture.

## What You Can Do

Once connected, Claude can:

- **Explore your architecture** - Discover services, their relationships, and how they connect
- **Analyze dependencies** - Understand what each service depends on and what depends on it
- **Investigate issues** - Trace request paths, find connection points, and debug problems
- **Plan changes** - Assess the impact of modifications before making them

## Example Queries

Try asking Claude:

**Discovery:**
```
What services exist in my system?
```

**Dependencies:**
```
What does the payment service depend on?
What would be affected if the user-service goes down?
```

**Investigation:**
```
How do requests flow from the API gateway to the database?
Find the path between the frontend and the order service.
```

**Architecture:**
```
Show me services that connect to the PostgreSQL database.
What are the most critical services in terms of dependencies?
```

## Troubleshooting

### "MCP server not found" Error

- Verify the `.mcp.json` file is in your project root or the global settings file exists
- Check that the JSON syntax is valid
- Restart Claude Code after making configuration changes

### "Unauthorized" Error

- Verify your API token is correct
- Check that the token hasn't expired
- Ensure the environment variable is set if using `${OPENTRACE_API_TOKEN}`

### No Data Returned

- Confirm you have integrations configured in OpenTrace (GitHub, GitLab, AWS EKS)
- Verify data has been synced from your integrations
- Check the OpenTrace dashboard to ensure your services are visible

## Next Steps

- [What You Can Do](../capabilities.md) - Full list of capabilities
- [Example Workflows](../workflows.md) - Common scenarios and approaches
- [GitHub Integration](github.md) - Connect your repositories
