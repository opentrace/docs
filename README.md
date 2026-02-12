# OpenTrace Documentation

Documentation site for [OpenTrace](https://opentrace.ai) — gives your AI assistant deep understanding of your system architecture so you can ask questions about services, dependencies, and how everything connects.

**Live site:** [docs.opentrace.com](https://docs.opentrace.com)

## Development

### Prerequisites

- Python 3.x

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

```
docs/
├── assets/                  # Images, logos, favicons
├── integrations/            # Integration guides (Claude Code, GitHub, GitLab, etc.)
├── snippets/                # Reusable documentation snippets
├── index.md                 # Home page
├── getting-started.md       # Setup and quick start
├── capabilities.md          # Full reference of supported queries
├── workflows.md             # Example use cases
├── otignore.md              # .otignore file documentation
├── privacy-policy.md        # Privacy policy
└── terms-of-service.md      # Terms of service
mkdocs.yml                   # MkDocs configuration
requirements.txt             # Python dependencies
```

## Deployment

Deployment is handled automatically via GitHub Actions.

- **Main branch** (`main`): Deploys to production at `https://docs.opentrace.com/`
- **All other branches**: Deploy to preview URLs at `https://docs.opentrace.com/preview/<branch-name>/`

Preview deployments are automatically cleaned up when their branch is deleted.

### Workflows

| Workflow | Trigger | Purpose |
|----------|---------|---------|
| `deploy.yml` | Push to any branch, PRs to main | Build and deploy the site |
| `cleanup-preview.yml` | Branch deletion | Remove preview deployments |
