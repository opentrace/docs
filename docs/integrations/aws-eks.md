# AWS EKS

Connect your AWS EKS clusters to analyze Kubernetes resources, deployments, and service topology.

## Prerequisites

- An AWS account with EKS clusters
- Permissions to create IAM roles and policies
- Access to configure EKS cluster access entries

## Setup Steps

### Step 1: Create an IAM Policy

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

### Step 2: Create an IAM Role

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

### Step 3: Configure EKS Access Entries

For each EKS cluster you want to connect:

1. Go to your EKS cluster in the AWS Console
2. Navigate to **Access** > **Access entries**
3. Click **Create access entry**
4. Enter the IAM Role ARN from Step 2
5. Add the `AmazonEKSViewPolicy` access policy

### Step 4: Connect in OpenTrace

1. Navigate to **Integrations > AWS EKS** in the OpenTrace UI
2. Enter your IAM Role ARN
3. Add your EKS cluster details (name and region)
4. Click **Connect**

## What Gets Collected

- Cluster configuration
- Namespace and deployment information
- Service topology
- Pod and container status
- Resource relationships

!!! warning "Data Collection"
    OpenTrace collects Kubernetes resource metadata only. No sensitive data like secrets or environment variables are accessed.
