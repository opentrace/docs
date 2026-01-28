# Grafana Tempo

!!! info "Early Access"
    This integration is in early access. Features and configuration may change.

Connect your Grafana Tempo instance to analyze distributed traces and understand request flows across your services.

## Overview

[Grafana Tempo](https://grafana.com/oss/tempo/) is a high-volume, cost-effective distributed tracing backend. OpenTrace integrates with Tempo to import trace data, enabling you to correlate traces with your code, infrastructure, and issues for deeper system understanding.

## Prerequisites

- A running Grafana Tempo instance with HTTP API access
- Network connectivity from OpenTrace to your Tempo endpoint
- (Optional) Credentials if your Tempo instance requires authentication

## Setup Steps

### Step 1: Get Your Tempo Endpoint URL

Locate your Tempo query frontend or gateway endpoint URL. This is typically in the format:

```
https://tempo.your-domain.com
```

If you're running Tempo in Kubernetes, this might be exposed via an ingress or load balancer.

### Step 2: Prepare Authentication (If Required)

If your Tempo instance requires authentication, gather your credentials:

- **Username**: Your Tempo authentication username
- **Password**: Your Tempo authentication password

OpenTrace uses HTTP Basic Authentication to connect to Tempo.

### Step 3: Connect in OpenTrace

1. Navigate to **Integrations > Grafana Tempo** in the OpenTrace UI
2. Enter your Tempo instance URL
3. (Optional) Enter your username and password if authentication is required
4. Click **Connect**

### Step 4: Verify the Connection

After connecting, OpenTrace will perform an initial sync to verify the connection and begin importing trace data. You can monitor the sync status on the integration page.

## What Gets Synced

OpenTrace synchronizes the following trace data from Tempo:

- **Traces**: Complete distributed traces showing request flows
- **Spans**: Individual operation spans within traces
- **Service relationships**: Service-to-service communication patterns derived from trace data
- **Operation metadata**: Service names, operation names, and timing information

This data is used to build a comprehensive view of your system's runtime behavior and service dependencies.

## Sync Schedule

After the initial sync, OpenTrace automatically synchronizes trace data on a configurable schedule. You can:

- View sync status and history on the integration page
- Manually trigger a sync using the **Sync** button
- Configure sync intervals in the Schedules tab

## Permissions Required

OpenTrace requires read access to your Tempo instance's HTTP API, specifically:

- Query API endpoints (`/api/traces/*`)
- Search API endpoints (if available)

No write access is required. OpenTrace only reads trace data from Tempo.

## Security Considerations

!!! warning "Data Access"
    OpenTrace accesses trace metadata and span information. If your traces contain sensitive data in span attributes or tags, ensure appropriate access controls are in place on your Tempo instance.

- Credentials are stored securely and encrypted at rest
- All communication with Tempo uses HTTPS (recommended)
- OpenTrace does not modify or delete any data in Tempo

## Grafana Cloud Users

If you're using Grafana Cloud Traces, you can also configure the Tempo MCP server to enable AI-powered trace exploration directly in your development tools. This allows natural language queries against your tracing data for diagnostics and performance optimization.

For setup instructions, see [Configure the MCP server for your AI tool](https://grafana.com/docs/grafana-cloud/send-data/traces/mcp-server/#configure-the-mcp-server-for-your-ai-tool) in the Grafana Cloud documentation.

## Troubleshooting

### Connection Failed

- Verify the Tempo URL is correct and accessible from OpenTrace
- Check that the URL uses the correct protocol (http/https)
- Ensure any firewalls or network policies allow traffic from OpenTrace

### Authentication Errors

- Confirm your username and password are correct
- Verify your Tempo instance is configured to accept Basic Authentication
- Check for any IP allowlists that might be blocking access

### No Data Appearing

- Ensure your Tempo instance has trace data available
- Check the sync status for any error messages
- Verify that your Tempo instance is receiving traces from your applications

### Sync Taking Too Long

- Large trace volumes may require more time for initial sync
- Consider using service filters to limit the scope of synced data
- Check the Schedules tab for sync progress details
