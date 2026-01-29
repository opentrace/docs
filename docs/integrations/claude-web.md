# Claude Web

Connect OpenTrace to Claude on the web to give your AI assistant deep knowledge about your system architecture.

## What is Claude Web?

Claude Web is Anthropic's web-based interface for Claude, available at [claude.ai](https://claude.ai). It provides access to Claude's capabilities directly in your browser without any installation required.

By connecting OpenTrace to Claude Web, you give Claude access to your system's architecture, service dependencies, and runtime relationships - enabling it to answer questions about your infrastructure and help debug issues.

## Prerequisites

- A [Claude Pro, Team, or Enterprise](https://claude.ai) subscription (MCP integrations require a paid plan)
- An OpenTrace account with an API token

## Setup Steps

### 1. Get Your API Token

1. Log in to the [OpenTrace dashboard](https://app.opentrace.ai)
2. Click on the **Organization Switcher** in the sidebar
3. Select **Manage organization** to open your organization profile
4. Navigate to **Service Accounts**
5. Click **Create Service Account** and give it a name (e.g., "Claude Web")
6. Click **Generate Token** on the service account you created
7. Copy the token - you'll need it in the next step

!!! warning
    The token is only displayed once. Make sure to copy it before closing the dialog.

### 2. Configure the MCP Integration

1. Go to [claude.ai](https://claude.ai) and sign in
2. Click on your profile icon in the bottom-left corner
3. Select **Settings**
4. Navigate to **Connectors** in the settings menu
5. Click **Add custom connector**
6. Select **MCP Server** as the integration type
7. Enter the following details:
    - **Name:** OpenTrace
    - **URL:** `https://api.opentrace.ai/mcp/v1`
    - **Authentication:** Bearer Token
    - **Token:** Paste your OpenTrace API token
8. Click **Save** to add the integration

### 3. Verify the Connection

Start a new conversation with Claude and ask:

> "What services are available in OpenTrace?"

If configured correctly, Claude will be able to query your system architecture.

!!! tip
    If Claude doesn't seem to use the OpenTrace integration, try explicitly mentioning it: "Using the OpenTrace integration, show me my services."

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

### Integration Not Appearing

- Refresh the page after adding the integration
- Check that you have a Claude Pro, Team, or Enterprise subscription
- Try removing and re-adding the integration

### "Unauthorized" Error

- Verify your API token is correct
- Check that the token hasn't expired
- Generate a new token if necessary

### No Data Returned

- Confirm you have integrations configured in OpenTrace (GitHub, GitLab, AWS EKS)
- Verify data has been synced from your integrations
- Check the OpenTrace dashboard to ensure your services are visible

### Claude Not Using the Integration

- Start a new conversation (integrations may not activate mid-conversation)
- Explicitly ask Claude to use OpenTrace in your query
- Verify the integration shows as "Connected" in your settings

## Next Steps

- [What You Can Do](../capabilities.md) - Full list of capabilities
- [Example Workflows](../workflows.md) - Common scenarios and approaches
- [GitHub Integration](github.md) - Connect your repositories
