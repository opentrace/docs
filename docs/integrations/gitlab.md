# GitLab

Connect GitLab to sync repository data and analyze code structure.

## Prerequisites

- A GitLab account (GitLab.com or self-hosted)
- Access to the projects you want to connect

## Setup Steps

1. Navigate to **Integrations > GitLab** in the OpenTrace UI
2. Click **Connect GitLab**
3. You'll be redirected to GitLab to authorize the application
4. Grant the requested permissions
5. Select the projects you want to sync

## What Gets Synced

- Project structure and files
- Code symbols and dependencies
- Issues

You can exclude specific files or directories from analysis using [`.otignore` files](../otignore.md).

## Self-Hosted GitLab

For self-hosted GitLab instances, you may need to configure the GitLab URL in your OpenTrace settings before connecting.
