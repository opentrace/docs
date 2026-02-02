# Claude Code

Connect OpenTrace to Claude Code to give your AI assistant deep knowledge about your system architecture.

## What is Claude Code?

Claude Code is Anthropic's official command-line interface for Claude. It enables Claude to understand your codebase, execute commands, and assist with software engineering tasks directly from your terminal.

By connecting OpenTrace to Claude Code, you give Claude access to your system's architecture, service dependencies, and runtime relationships - enabling it to answer questions about your infrastructure and help debug issues.

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and configured
- An OpenTrace account

## Authentication Methods

OpenTrace supports two authentication methods for Claude Code:

| Method | Best For | How It Works |
|--------|----------|--------------|
| **OAuth** (Recommended) | Interactive use by developers | Browser opens for authorization, tokens managed automatically |
| **API Token** | Automation, CI/CD, headless environments | Service account token configured manually |

## Option A: OAuth Authentication (Recommended)

OAuth is the recommended method for developers using Claude Code interactively. When you connect, Claude Code opens your browser to authorize access, and handles token management automatically.

### Quick Setup

Run the following command to add OpenTrace with OAuth:

```bash
claude mcp add opentrace --transport http https://api.opentrace.ai/mcp/v1
```

When you first use the integration, Claude Code will:

1. Open your browser to the OpenTrace authorization page
2. Prompt you to sign in (if not already signed in)
3. Ask you to select an organization and confirm permissions
4. Automatically receive and store the authentication token

!!! note
    Claude Code runs a temporary local server to receive the OAuth callback. Your browser will be redirected to `127.0.0.1` to complete the authorization.

By default, this adds the server to your user configuration (available in all sessions). To add it to a specific project only, use the `--scope` flag:

```bash
claude mcp add opentrace --transport http https://api.opentrace.ai/mcp/v1 --scope project
```

### Manual Configuration (OAuth)

You can also configure OAuth manually by creating or editing configuration files.

**Project-Level Configuration**

Create a `.mcp.json` file in your project root:

```json
{
  "mcpServers": {
    "opentrace": {
      "type": "http",
      "url": "https://api.opentrace.ai/mcp/v1"
    }
  }
}
```

**Global Configuration**

Edit `~/.claude/settings.json` (macOS/Linux) or `%USERPROFILE%\.claude\settings.json` (Windows):

```json
{
  "mcpServers": {
    "opentrace": {
      "type": "http",
      "url": "https://api.opentrace.ai/mcp/v1"
    }
  }
}
```

## Option B: API Token Authentication

API tokens are recommended for automated environments such as CI/CD pipelines, scripts, or headless servers where browser-based OAuth isn't possible.

### 1. Get Your API Token

1. Log in to the [OpenTrace dashboard](https://app.opentrace.ai)
2. Click on the **Organization Switcher** in the sidebar
3. Select **Manage organization** to open your organization profile
4. Navigate to **Service Accounts**
5. Click **Create Service Account** and give it a name (e.g., "Claude Code CI")
6. Click **Generate Token** on the service account you created
7. Copy the token - you'll need it in the next step

!!! warning
    The token is only displayed once. Make sure to copy it before closing the dialog.

### 2. Configure MCP with API Token

#### Command-Line Configuration

```bash
claude mcp add opentrace \
  --transport http \
  https://api.opentrace.ai/mcp/v1 \
  --header "Authorization: Bearer YOUR_API_TOKEN"
```

Replace `YOUR_API_TOKEN` with your OpenTrace API token.

!!! tip
    Use an environment variable to avoid exposing your token in shell history:
    ```bash
    claude mcp add opentrace \
      --transport http \
      https://api.opentrace.ai/mcp/v1 \
      --header "Authorization: Bearer ${OPENTRACE_API_TOKEN}"
    ```

#### Project-Level Configuration

Create a `.mcp.json` file in your project root:

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

Then set the environment variable:

```bash
export OPENTRACE_API_TOKEN=your_token_here
```

#### Global Configuration

Edit `~/.claude/settings.json` (macOS/Linux) or `%USERPROFILE%\.claude\settings.json` (Windows):

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

## Verify the Connection

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
- Run `claude mcp list` to see all configured MCP servers

### OAuth Authorization Failed

- Ensure your browser can open URLs from the terminal
- Check that pop-ups are not blocked
- Verify you have access to the OpenTrace organization
- Try removing the server with `claude mcp remove opentrace` and adding it again

### "Unauthorized" Error (API Token)

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
