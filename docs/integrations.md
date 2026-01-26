# Integrations

OpenTrace connects to your existing tools and infrastructure to build a complete picture of your system. This guide covers how to set up each integration.

## Overview

| Integration | Type | What It Provides |
|-------------|------|------------------|
| [GitHub](#github) | OAuth | Repository data, issues, PRs, code analysis |
| [GitLab](#gitlab) | OAuth | Repository data, issues, MRs, code analysis |
| [AWS EKS](#aws-eks) | IAM Role | Kubernetes cluster topology and resources |

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

---

## Next Steps

- [Getting Started](getting-started.md) - Set up OpenTrace
- [What You Can Do](capabilities.md) - Learn about available queries
- [Example Workflows](workflows.md) - See integrations in action
