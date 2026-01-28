# Claude Code

Connect OpenTrace to Claude Code to give your AI assistant deep knowledge about your system architecture.

## What is Claude Code?

Claude Code is Anthropic's official command-line interface for Claude. It enables Claude to understand your codebase, execute commands, and assist with software engineering tasks directly from your terminal.

By connecting OpenTrace to Claude Code, you give Claude access to your system's architecture, service dependencies, and runtime relationships - enabling it to answer questions about your infrastructure and help debug issues.

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and configured
- An OpenTrace account

## Setup Steps

OpenTrace supports two authentication methods for Claude Code:

| Method | Best For |
|--------|----------|
| [OAuth Flow](#method-a-oauth-flow-recommended) | Personal use, quick setup, automatic token refresh |
| [API Token](#method-b-api-token) | CI/CD, shared configurations, service accounts |

### Method A: OAuth Flow (Recommended)

OAuth lets you authenticate through your browser without manually managing tokens.

#### 1. Configure MCP with OAuth

Add the OpenTrace server to your Claude Code configuration with OAuth authentication.

**Project-level** (`.mcp.json` in your project root):

```json
{
  "mcpServers": {
    "opentrace": {
      "type": "http",
      "url": "https://api.opentrace.ai/mcp/v1/oauth"
    }
  }
}
```

**Global** (`~/.claude/settings.json` on macOS/Linux or `%USERPROFILE%\.claude\settings.json` on Windows):

```json
{
  "mcpServers": {
    "opentrace": {
      "type": "http",
      "url": "https://api.opentrace.ai/mcp/v1/oauth"
    }
  }
}
```

#### 2. Authenticate

Start Claude Code:

```bash
claude
```

When you first use an OpenTrace tool, Claude Code will prompt you to authenticate:

1. A browser window opens automatically
2. Log in to your OpenTrace account (or confirm if already logged in)
3. Authorize Claude Code to access your organization
4. Return to your terminal - authentication is complete

!!! tip
    Your OAuth session persists across Claude Code sessions. You'll only need to re-authenticate if your session expires or you revoke access.

#### 3. Verify the Connection

Ask Claude to verify the connection:

> "What services are available in OpenTrace?"

If configured correctly, Claude will be able to query your system architecture.

---

### Method B: API Token

Use API tokens for service accounts, CI/CD pipelines, or shared team configurations.

#### 1. Get Your API Token

1. Log in to the [OpenTrace dashboard](https://app.opentrace.ai)
2. Click on the **Organization Switcher** in the sidebar
3. Select **Manage organization** to open your organization profile
4. Navigate to **Service Accounts**
5. Click **Create Service Account** and give it a name (e.g., "Claude Code")
6. Click **Generate Token** on the service account you created
7. Copy the token - you'll need it in the next step

!!! warning
    The token is only displayed once. Make sure to copy it before closing the dialog.

#### 2. Configure MCP

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

#### 3. Verify the Connection

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

### OAuth Browser Doesn't Open

- Check that your default browser is configured correctly
- Try manually opening the authorization URL shown in the terminal
- Ensure pop-ups are not blocked for `app.opentrace.ai`

### OAuth Session Expired

- Re-authenticate by running any OpenTrace query - Claude Code will prompt you to log in again
- If issues persist, remove the cached OAuth tokens and restart Claude Code

### "Unauthorized" Error

**For API Token authentication:**

- Verify your API token is correct
- Check that the token hasn't expired
- Ensure the environment variable is set if using `${OPENTRACE_API_TOKEN}`

**For OAuth authentication:**

- Your session may have expired - try re-authenticating
- Verify you authorized the correct OpenTrace organization
- Check that your OpenTrace account has access to the organization

### No Data Returned

- Confirm you have integrations configured in OpenTrace (GitHub, GitLab, AWS EKS)
- Verify data has been synced from your integrations
- Check the OpenTrace dashboard to ensure your services are visible

## Next Steps

- [What You Can Do](../capabilities.md) - Full list of capabilities
- [Example Workflows](../workflows.md) - Common scenarios and approaches
- [GitHub Integration](github.md) - Connect your repositories
