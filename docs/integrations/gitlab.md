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

## Changing the Synced Branch

By default, OpenTrace syncs the default branch of each project (typically `main` or `master`). You can change which branch is synced for any project through the UI or API.

### Using the UI

1. Navigate to **Integrations > GitLab** in the OpenTrace UI
2. Find the project you want to configure
3. Click the project to open its sync settings
4. Click the edit icon (✏️) next to the **Branch** field
5. Enter the new branch name (e.g., `develop`, `staging`, `feature/new-ui`)
6. Click the checkmark (✓) to save
7. Confirm the change by typing the project name when prompted

**Important Notes:**

- Changing the branch will trigger a reindex of the project code
- All existing code index data for that project will be removed
- The reindexing process may take several minutes depending on project size
- The branch must exist in the project before you can sync it

### Using the API

You can also change the branch programmatically using the API.  This is documented under [api.opentrace.ai/openapi](https://api.opentrace.ai/openapi/) - see the section on integrations.

### Branch Configuration Behavior

- **First-time sync**: Uses the project's default branch from GitLab
- **Custom branch**: Once set, OpenTrace continues using your configured branch
- **Branch deletion**: If the configured branch is deleted, syncing will fail until you update to a valid branch
- **Empty value**: Setting `code_branch` to an empty string or removing it will revert to using the project's default branch
