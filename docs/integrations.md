# Integrations

OpenTrace connects to your existing tools and infrastructure to build a complete picture of your system. This guide covers how to set up each integration.

## Overview

| Integration | Type | What It Provides |
|-------------|------|------------------|
| [GitHub](#github) | OAuth | Repository data, issues, PRs, code analysis |
| [GitLab](#gitlab) | OAuth | Repository data, issues, MRs, code analysis |
| [Slack](#slack) | OAuth | Notifications and alerts |
| [AWS EKS](#aws-eks) | IAM Role | Kubernetes cluster topology and resources |
| [Grafana](#grafana) | API Key | Logs (Loki) and metrics (Mimir/Prometheus) |
| [Jaeger](#jaeger) | API | Distributed tracing data |
| [OpenSearch](#opensearch) | API | Log search and analysis |
| [MCP Servers](#mcp-servers) | Local | AI assistant integrations |

---

## GitHub

Connect GitHub to sync repository data, analyze code structure, and track issues and pull requests.

### Prerequisites

- A GitHub account with access to the repositories you want to connect
- Admin access to install GitHub Apps (for organization repositories)

### Setup Steps

1. Navigate to **Integrations > GitHub** in the OpenTrace UI
2. Click **Connect GitHub**
3. You'll be redirected to GitHub to authorize the OpenTrace GitHub App
4. Select the repositories or organizations you want to connect
5. Click **Authorize** to complete the OAuth flow

### What Gets Synced

- Repository structure and files
- Code symbols and dependencies
- Issues and pull requests
- Commit history
- Branch information

### Permissions Required

OpenTrace requests read-only access to:

- Repository contents
- Issues and pull requests
- Organization membership (for org repos)

---

## GitLab

Connect GitLab to sync repository data, analyze code, and track issues and merge requests.

### Prerequisites

- A GitLab account (GitLab.com or self-hosted)
- Access to the projects you want to connect

### Setup Steps

1. Navigate to **Integrations > GitLab** in the OpenTrace UI
2. Click **Connect GitLab**
3. You'll be redirected to GitLab to authorize the application
4. Grant the requested permissions
5. Select the projects you want to sync

### What Gets Synced

- Project structure and files
- Code symbols and dependencies
- Issues and merge requests
- CI/CD pipeline information

### Self-Hosted GitLab

For self-hosted GitLab instances, you may need to configure the GitLab URL in your OpenTrace settings before connecting.

---

## Slack

Connect Slack to receive notifications and alerts from OpenTrace directly in your workspace.

### Prerequisites

- A Slack workspace where you have permission to install apps
- Admin approval may be required for workspace-wide installations

### Setup Steps

1. Navigate to **Integrations > Slack** in the OpenTrace UI
2. Click **Connect to Slack**
3. Select your Slack workspace from the dropdown
4. Choose which channel(s) to post notifications to
5. Click **Allow** to authorize the integration

### Features

Once connected, you can:

- Receive alerts about system changes
- Get notified about investigation findings
- Share insights with your team

### Verifying the Connection

After setup, OpenTrace will send a test message to your selected channel to confirm the integration is working.

---

## AWS EKS

Connect your AWS EKS clusters to analyze Kubernetes resources, deployments, and service topology.

### Prerequisites

- An AWS account with EKS clusters
- Permissions to create IAM roles and policies
- Access to configure EKS cluster access entries

### Setup Steps

#### Step 1: Create an IAM Policy

Create a custom IAM policy with the following permissions:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "eks:DescribeCluster",
        "eks:ListClusters",
        "eks:AccessKubernetesApi"
      ],
      "Resource": "*"
    }
  ]
}
```

#### Step 2: Create an IAM Role

1. Create a new IAM role for web identity federation
2. Configure the trust relationship to allow OpenTrace to assume the role:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Federated": "accounts.google.com"
      },
      "Action": "sts:AssumeRoleWithWebIdentity",
      "Condition": {
        "StringEquals": {
          "accounts.google.com:aud": "YOUR_OPENTRACE_CLIENT_ID"
        }
      }
    }
  ]
}
```

3. Attach the policy created in Step 1 to this role
4. Note the Role ARN for the next steps

#### Step 3: Configure EKS Access Entries

For each EKS cluster you want to connect:

1. Go to your EKS cluster in the AWS Console
2. Navigate to **Access** > **Access entries**
3. Click **Create access entry**
4. Enter the IAM Role ARN from Step 2
5. Add the `AmazonEKSViewPolicy` access policy

#### Step 4: Connect in OpenTrace

1. Navigate to **Integrations > AWS EKS** in the OpenTrace UI
2. Enter your IAM Role ARN
3. Add your EKS cluster details (name and region)
4. Click **Connect**

### What Gets Collected

- Cluster configuration
- Namespace and deployment information
- Service topology
- Pod and container status
- Resource relationships

!!! warning "Data Collection"
    OpenTrace collects Kubernetes resource metadata only. No sensitive data like secrets or environment variables are accessed.

---

## Grafana

Connect Grafana to query logs from Loki and metrics from Mimir/Prometheus.

### Prerequisites

- A Grafana instance (Cloud or self-hosted)
- API access enabled on your Grafana instance
- Loki and/or Mimir/Prometheus data sources configured

### Setup Steps

1. Navigate to **Integrations > Grafana** in the OpenTrace UI
2. Enter your Grafana instance URL
3. Generate a Service Account token in Grafana:
   - Go to **Administration > Service Accounts**
   - Create a new service account
   - Add a token with `Viewer` role
4. Enter the token in OpenTrace
5. Click **Connect**

### Configuration Options

| Field | Description |
|-------|-------------|
| **URL** | Your Grafana instance URL (e.g., `https://your-org.grafana.net`) |
| **API Token** | Service account token with Viewer access |

### Available Data Sources

Once connected, OpenTrace can query:

- **Loki**: Log data using LogQL queries
- **Mimir/Prometheus**: Metrics data using PromQL queries

### Example Queries

OpenTrace will automatically use Grafana to help answer questions like:

- "Show me error logs from the payment service"
- "What's the CPU usage trend for the API?"
- "Find logs mentioning timeout errors"

---

## Jaeger

Connect Jaeger to analyze distributed traces across your services.

### Prerequisites

- A running Jaeger instance
- Network access to Jaeger's Query API

### Setup Steps

1. Navigate to **Integrations > Jaeger** in the OpenTrace UI
2. Enter your Jaeger Query URL:
   - HTTP API: `http://jaeger-query:16686`
   - gRPC API: `jaeger-query:16685`
3. (Optional) Add authentication headers if required
4. Click **Connect**

### Configuration Options

| Field | Description |
|-------|-------------|
| **URL** | Jaeger Query service URL |
| **Auth Header** | Optional authentication header |

### What You Can Do

With Jaeger connected, you can:

- Search for traces by service, operation, or tags
- Analyze trace duration and latency
- View service dependency graphs
- Identify slow spans and bottlenecks

### Supported Protocols

OpenTrace supports both:

- **HTTP API**: Standard REST API on port 16686
- **gRPC API**: For higher performance on port 16685

---

## OpenSearch

Connect OpenSearch to search and analyze logs.

### Prerequisites

- An OpenSearch cluster
- Network access to the OpenSearch API
- Read permissions for the indices you want to query

### Setup Steps

1. Navigate to **Integrations > OpenSearch** in the OpenTrace UI
2. Enter your OpenSearch cluster URL
3. Provide authentication credentials:
   - Basic auth (username/password), or
   - API key
4. Specify the index patterns to query
5. Click **Connect**

### Configuration Options

| Field | Description |
|-------|-------------|
| **URL** | OpenSearch cluster URL |
| **Username** | Basic auth username |
| **Password** | Basic auth password |
| **Index Pattern** | Index pattern to query (e.g., `logs-*`) |

---

## MCP Servers

OpenTrace provides Model Context Protocol (MCP) servers that allow AI assistants like Claude to query your system data.

### Overview

MCP servers act as a bridge between AI assistants and your observability data. They expose tools that let the AI:

- Query the knowledge graph
- Search logs and traces
- Analyze system topology

### Local Development Setup

Use the **Insight MCP Manager** to run MCP servers locally:

```bash
# Install the MCP manager
npm install -g @opentrace/mcp-manager

# Initialize configuration
insight-mcp init

# Start MCP servers
insight-mcp start
```

### Available MCP Servers

| Server | Purpose |
|--------|---------|
| **OpenTrace MCP** | Query the knowledge graph |
| **Grafana MCP** | Query Loki logs and Prometheus metrics |
| **Jaeger MCP** | Search and analyze traces |
| **GitHub MCP** | Access repository data |

### Claude Desktop Configuration

Add to your Claude Desktop config (`~/.config/claude/claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "opentrace": {
      "command": "insight-mcp",
      "args": ["start", "--server", "opentrace"]
    }
  }
}
```

### VS Code Configuration

For Claude in VS Code, add to your settings:

```json
{
  "claude.mcpServers": {
    "opentrace": {
      "command": "insight-mcp",
      "args": ["start", "--server", "opentrace"]
    }
  }
}
```

### Environment Variables

Configure MCP servers using environment variables:

| Variable | Description |
|----------|-------------|
| `INSIGHT_API_URL` | OpenTrace API endpoint |
| `INSIGHT_API_TOKEN` | API authentication token |
| `GRAFANA_URL` | Grafana instance URL |
| `GRAFANA_TOKEN` | Grafana API token |
| `JAEGER_URL` | Jaeger Query URL |

---

## Troubleshooting

### Connection Issues

**OAuth integrations (GitHub, GitLab, Slack)**

- Ensure pop-ups are not blocked in your browser
- Check that you have the required permissions
- Try disconnecting and reconnecting

**API integrations (Grafana, Jaeger, OpenSearch)**

- Verify the URL is correct and accessible
- Check that credentials have sufficient permissions
- Ensure network/firewall rules allow the connection

**AWS EKS**

- Verify the IAM role trust relationship is correctly configured
- Ensure EKS access entries are created for each cluster
- Check that the role has the required permissions

### Refreshing Data

Most integrations sync automatically. To force a refresh:

1. Go to the integration's management page
2. Click the **Sync** button
3. Wait for the sync to complete

### Disconnecting an Integration

1. Navigate to the integration page
2. Click **Disconnect**
3. Confirm the disconnection

!!! note
    Disconnecting an integration removes synced data from OpenTrace but does not affect your external service.

---

## Next Steps

- [Getting Started](getting-started.md) - Set up OpenTrace
- [What You Can Do](capabilities.md) - Learn about available queries
- [Example Workflows](workflows.md) - See integrations in action
