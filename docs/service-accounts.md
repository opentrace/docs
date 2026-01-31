# Service Accounts

Service accounts enable programmatic access to OpenTrace APIs and integrations. This guide explains how to create and manage service accounts for your organization.

## What are Service Accounts?

Service accounts are non-human identities used to authenticate applications, scripts, and integrations with OpenTrace. Unlike user accounts that are tied to individuals, service accounts are designed for:

- **AI assistants** - Claude Code, GitHub Copilot, and other AI tools that need to query your architecture
- **CI/CD pipelines** - Automated workflows that interact with OpenTrace
- **Custom integrations** - Applications you build that use the OpenTrace API

Each service account can have one or more API tokens that grant access to your organization's data.

## Creating a Service Account

Follow these steps to create a service account and generate an API token:

1. Log in to the [OpenTrace dashboard](https://app.opentrace.ai)
2. Click on the **Organization Switcher** in the sidebar
3. Select **Manage organization** to open your organization profile
4. Navigate to the **Service Accounts** tab
5. Click **Create Service Account**
6. Enter a descriptive name for the service account (e.g., "Claude Code", "CI Pipeline", "Production Monitoring")
7. Click **Create** to save the service account

### Generating an API Token

Once your service account is created:

1. Find the service account in the list
2. Click **Generate Token**
3. Copy the token immediately

!!! warning "Token Security"
    The token is only displayed once. Make sure to copy it before closing the dialog. If you lose the token, you'll need to generate a new one.

## Managing Service Accounts

### Viewing Service Accounts

All service accounts for your organization are listed on the **Service Accounts** tab in your organization settings. Each entry shows:

- Service account name
- Creation date
- Number of active tokens
- Last used timestamp

### Revoking Tokens

If a token is compromised or no longer needed:

1. Navigate to **Organization Settings** > **Service Accounts**
2. Find the service account
3. Click on the token you want to revoke
4. Click **Revoke Token**

!!! note
    Revoking a token immediately invalidates it. Any integrations using that token will stop working until configured with a new token.

### Deleting a Service Account

To remove a service account entirely:

1. Navigate to **Organization Settings** > **Service Accounts**
2. Find the service account
3. Click the **Delete** button
4. Confirm the deletion

!!! warning
    Deleting a service account revokes all its tokens and cannot be undone.

## Best Practices

### Naming Conventions

Use clear, descriptive names that indicate the purpose:

| Good Examples | Why |
|--------------|-----|
| `claude-code-dev-team` | Indicates tool and team |
| `github-actions-prod` | Indicates CI system and environment |
| `monitoring-service` | Indicates purpose |

| Avoid | Why |
|-------|-----|
| `test` | Too vague |
| `api-key-1` | Doesn't describe purpose |
| `john-token` | Service accounts shouldn't be tied to individuals |

### Token Security

**Store tokens securely:**

- Use environment variables instead of hardcoding tokens
- Store tokens in secret managers (AWS Secrets Manager, HashiCorp Vault, etc.)
- Never commit tokens to version control

**Example using environment variables:**

```bash
# Set the environment variable
export OPENTRACE_API_TOKEN=your_token_here

# Reference in configuration
# The token is read from the environment at runtime
```

**Example `.gitignore` to prevent accidental commits:**

```gitignore
# Environment files with secrets
.env
.env.local
*.env

# MCP configuration with hardcoded tokens
.mcp.json
```

### Principle of Least Privilege

- Create separate service accounts for different purposes
- Use dedicated service accounts for production vs. development
- Revoke tokens that are no longer needed

### Regular Audits

- Review service accounts periodically
- Remove unused service accounts
- Rotate tokens for long-running integrations

## Using API Tokens

### Authentication

Include your API token in the `Authorization` header:

```
Authorization: Bearer YOUR_API_TOKEN
```

### MCP Configuration

For AI assistants like Claude Code, configure the token in your MCP settings:

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

See the [Claude Code integration guide](integrations/claude-code.md) for detailed setup instructions.

## Troubleshooting

### "Unauthorized" Error (401)

- Verify the token is correct and hasn't been revoked
- Check that the `Authorization` header is properly formatted
- Ensure the environment variable is set if using variable substitution

### "Forbidden" Error (403)

- The service account may not have access to the requested resource
- Check that the service account belongs to the correct organization

### Token Not Working After Generation

- Tokens take effect immediately - no delay expected
- Verify you copied the complete token without extra spaces
- Try generating a new token if issues persist

## Next Steps

- [Claude Code Integration](integrations/claude-code.md) - Connect OpenTrace to Claude Code
- [GitHub Copilot Integration](integrations/github-copilot.md) - Connect OpenTrace to GitHub Copilot
- [What You Can Do](capabilities.md) - Explore OpenTrace capabilities
