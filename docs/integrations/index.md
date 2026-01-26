# Integrations

OpenTrace connects to your existing tools and infrastructure to build a complete picture of your system.

## Available Integrations

| Integration | Type | What It Provides | Status |
|-------------|------|------------------|--------|
| [GitHub](github.md) | OAuth | Repository data, issues, code analysis | |
| [GitLab](gitlab.md) | OAuth | Repository data, issues, code analysis | |
| [AWS EKS](aws-eks.md) | IAM Role | Kubernetes cluster topology and resources | Early Access |

## Troubleshooting

### Connection Issues

**OAuth integrations (GitHub, GitLab)**

- Ensure pop-ups are not blocked in your browser
- Check that you have the required permissions
- Try disconnecting and reconnecting

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
