# GitHub Copilot

Connect OpenTrace to GitHub Copilot in VS Code to give your AI assistant deep knowledge about your system architecture.

## What is GitHub Copilot?

GitHub Copilot is an AI-powered coding assistant developed by GitHub and OpenAI. When used in Visual Studio Code, it provides code completions, chat assistance, and can help with a wide range of software engineering tasks.

By connecting OpenTrace to GitHub Copilot, you give it access to your system's architecture, service dependencies, and runtime relationships - enabling it to answer questions about your infrastructure and help debug issues.

## Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/) installed
- [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) installed and configured
- A GitHub Copilot subscription (Individual, Business, or Enterprise)
- An OpenTrace account

## Authentication Methods

OpenTrace supports two authentication methods for GitHub Copilot:

| Method | Best For | How It Works |
|--------|----------|--------------|
| **OAuth** (Recommended) | Interactive use by developers | Browser opens for authorization, tokens managed automatically |
| **API Token** | Automation, CI/CD, headless environments | Service account token configured manually |

## Option A: OAuth Authentication (Recommended)

OAuth is the recommended method for developers using GitHub Copilot interactively. When you connect, VS Code opens your browser to authorize access, and handles token management automatically.

### Workspace Configuration (OAuth)

Create a `.vscode/mcp.json` file in your workspace root:

```json
{
  "servers": {
    "opentrace": {
      "type": "http",
      "url": "https://api.opentrace.ai/mcp/v1"
    }
  }
}
```

When you first use the integration, VS Code will:

1. Open your browser to the OpenTrace authorization page
2. Prompt you to sign in (if not already signed in)
3. Ask you to select an organization and confirm permissions
4. Automatically receive and store the authentication token

!!! note
    VS Code runs a temporary local server to receive the OAuth callback. Your browser will be redirected to `127.0.0.1` to complete the authorization.

### Global Configuration (OAuth)

To make OpenTrace available across all your VS Code workspaces with OAuth:

1. Open VS Code Settings (`Cmd+,` on macOS, `Ctrl+,` on Windows/Linux)
2. Search for "mcp" in the settings search bar
3. Click **Edit in settings.json**
4. Add the following configuration:

```json
{
  "github.copilot.chat.mcp.servers": {
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
5. Click **Create Service Account** and give it a name (e.g., "VS Code")
6. Click **Generate Token** on the service account you created
7. Copy the token - you'll need it in the next step

!!! warning
    The token is only displayed once. Make sure to copy it before closing the dialog.

### 2. Configure MCP with API Token

#### Workspace Configuration

Create a `.vscode/mcp.json` file in your workspace root:

```json
{
  "servers": {
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
    Use an environment file to avoid committing your token. Create a `.env` file in your workspace root:
    ```
    OPENTRACE_API_TOKEN=your_token_here
    ```
    Then reference it in your configuration:
    ```json
    {
      "servers": {
        "opentrace": {
          "type": "http",
          "url": "https://api.opentrace.ai/mcp/v1",
          "headers": {
            "Authorization": "Bearer ${env:OPENTRACE_API_TOKEN}"
          },
          "envFile": "${workspaceFolder}/.env"
        }
      }
    }
    ```
    Make sure to add `.env` to your `.gitignore` file.

#### Global Configuration

To make OpenTrace available across all your VS Code workspaces with an API token:

1. Open VS Code Settings (`Cmd+,` on macOS, `Ctrl+,` on Windows/Linux)
2. Search for "mcp" in the settings search bar
3. Click **Edit in settings.json**
4. Add the following configuration:

```json
{
  "github.copilot.chat.mcp.servers": {
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

!!! note
    Global settings do not support input variables for secrets. Consider using workspace configuration if you need to avoid storing the token in settings.

## Verify the Connection

1. Open the Copilot Chat panel in VS Code (`Cmd+Shift+I` on macOS, `Ctrl+Shift+I` on Windows/Linux)
2. Ask Copilot to verify the connection:

> "What services are available in OpenTrace?"

If configured correctly, Copilot will be able to query your system architecture.

!!! tip
    You may need to reload VS Code after configuring MCP for the changes to take effect.

## What You Can Do

Once connected, GitHub Copilot can:

- **Explore your architecture** - Discover services, their relationships, and how they connect
- **Analyze dependencies** - Understand what each service depends on and what depends on it
- **Investigate issues** - Trace request paths, find connection points, and debug problems
- **Plan changes** - Assess the impact of modifications before making them

## Example Queries

Try asking Copilot in the chat panel:

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

### MCP Server Not Connecting

- Verify the `.vscode/mcp.json` file exists in your workspace root
- Check that the JSON syntax is valid
- Reload VS Code after making configuration changes (`Cmd+Shift+P` → "Developer: Reload Window")

### OAuth Authorization Failed

- Ensure your browser can open URLs from VS Code
- Check that pop-ups are not blocked
- Verify you have access to the OpenTrace organization
- Try removing the configuration and re-adding it

### "Unauthorized" Error (API Token)

- Verify your API token is correct
- Check that the token hasn't expired
- If using `envFile`, ensure the `.env` file exists and contains the correct token
- Restart VS Code after making configuration changes

### No Data Returned

- Confirm you have integrations configured in OpenTrace (GitHub, GitLab, AWS EKS)
- Verify data has been synced from your integrations
- Check the OpenTrace dashboard to ensure your services are visible

### Copilot Not Using the Integration

- Make sure you're using the Copilot Chat panel, not inline completions
- Try explicitly mentioning OpenTrace in your query
- Check that the MCP extension is enabled in VS Code

## Next Steps

- [What You Can Do](../capabilities.md) - Full list of capabilities
- [Example Workflows](../workflows.md) - Common scenarios and approaches
- [GitHub Integration](github.md) - Connect your repositories
