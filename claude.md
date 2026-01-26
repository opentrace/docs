# OpenTrace Documentation

This is the documentation site for OpenTrace, built with MkDocs Material and hosted on GitHub Pages.

## Tech Stack

- **Framework**: MkDocs with Material theme
- **Hosting**: GitHub Pages
- **CI/CD**: GitHub Actions

## Development

### Local Development

```bash
# Install dependencies
pip install -r requirements.txt

# Start local dev server (runs on http://127.0.0.1:3009)
mkdocs serve

# Build static site
mkdocs build
```

### Project Structure

- `docs/` - Markdown documentation files
- `mkdocs.yml` - MkDocs configuration
- `.github/workflows/` - Deployment workflows

## Branch Deployments

This project supports automatic preview deployments for all branches pushed to the repository.

### How It Works

1. **Main branch** (`main`): Deploys to the production site at `https://docs.opentrace.com/`
2. **All other branches**: Deploy to preview URLs at `https://docs.opentrace.com/preview/<sanitized-branch-name>/`

### Preview URL Format

Branch names are sanitized for the URL path - non-alphanumeric characters (except hyphens) are replaced with hyphens.

| Branch Name | Preview URL |
|-------------|-------------|
| `feature/new-docs` | `https://docs.opentrace.com/preview/feature-new-docs/` |
| `claude/my-task-abc123` | `https://docs.opentrace.com/preview/claude-my-task-abc123/` |
| `fix_something` | `https://docs.opentrace.com/preview/fix-something/` |

### Verifying Your Changes

1. Push your branch to the repository
2. Wait for the GitHub Actions workflow to complete (check the Actions tab)
3. Access your preview at: `https://docs.opentrace.com/preview/<your-sanitized-branch>/`
4. The deployment URL is also shown in the GitHub Actions workflow summary

### Cleanup

Preview deployments are automatically cleaned up when branches starting with `preview/` are deleted. For other branches, cleanup can be triggered manually via the "Cleanup Preview Deployment" workflow.

## Deployment Workflows

### `deploy.yml`
- Triggers on: push to any branch, PRs to main, manual dispatch
- Builds the MkDocs site and deploys to GitHub Pages
- Main branch: root deployment
- Other branches: preview deployment in `preview/<branch>/` subfolder

### `cleanup-preview.yml`
- Triggers on: branch deletion (for `preview/*` branches), manual dispatch
- Removes preview folders from gh-pages when branches are deleted
