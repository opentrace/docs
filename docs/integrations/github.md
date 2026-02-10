# GitHub

Connect GitHub to sync repository data and analyze code structure.

## Prerequisites

- A GitHub account with access to the repositories you want to connect
- Admin access to install GitHub Apps (for organization repositories)

## Setup Steps

1. Navigate to **Integrations > GitHub** in the OpenTrace UI
2. Click **Connect GitHub**
3. You'll be redirected to GitHub to authorize the OpenTrace GitHub App
4. Select the repositories or organizations you want to connect
5. Click **Authorize** to complete the OAuth flow

## What Gets Synced

- Repository structure and files
- Code symbols and dependencies
- Issues

You can exclude specific files or directories from analysis using [`.otignore` files](../otignore.md).

## Permissions Required

OpenTrace requests read-only access to:

- Repository contents
- Issues
- Organization membership (for org repos)

## Changing the Synced Branch

By default, OpenTrace syncs the default branch of each repository (typically `main` or `master`). You can change which branch is synced for any repository through the UI or API.

### Using the UI

1. Navigate to **Integrations > GitHub** in the OpenTrace UI
2. Find the repository you want to configure under **Syncs**
3. Click the 3 vertical dots and open its sync settings
4. Click the edit icon (✏️) next to the **Branch** field
5. Enter the new branch name (e.g., `develop`, `staging`, `feature/new-ui`)
6. Click the checkmark (✓) to save
7. Confirm the change by typing the repository name when prompted

**Important Notes:**

- Changing the branch will trigger a reindex of the repository code
- All existing code index data for that repository will be removed
- The reindexing process may take several minutes depending on repository size
- The branch must exist in the repository before you can sync it

### Using the API

You can also change the branch programmatically using the API.  This is documented under [api.opentrace.ai/openapi](https://api.opentrace.ai/openapi/) - see the section on integrations.

### Branch Configuration Behavior

- **First-time sync**: Uses the repository's default branch from GitHub
- **Custom branch**: Once set, OpenTrace continues using your configured branch
- **Branch deletion**: If the configured branch is deleted, syncing will fail until you update to a valid branch
- **Empty value**: Setting `code_branch` to an empty string or removing it will revert to using the repository's default branch
