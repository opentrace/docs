# Features

When you click **Upload to Cloud** in the OpenTrace desktop app, your graph is saved to your OpenTrace account and you are brought here. The cloud version adds persistent storage, organisation-wide sharing, and the ability to organise your work into projects.

## Getting access

Access to OpenTrace cloud is by invitation. To request access, submit your email address directly from the login dialog. You will receive an email when your request is approved.

When you sign up you will be asked to create an organisation. The organisation is the shared space for your team — everyone you invite will have access to the same projects.

## Projects

A project is a named workspace that holds one or more indexed repositories together as a single graph. You can have as many projects as you like — for example, one per investigation, one per team, or one per product area. Repositories can appear in multiple projects, so different teams can each have their own view of a shared codebase without interfering with each other.

When you arrive from the desktop app, you will be prompted to save your graph into a new or existing project. Once saved, the graph is available to everyone in your organisation and persists across page reloads.

The project switcher in the sidebar lists your recent projects. Opening a different project replaces the active workspace — your conversation history and session activity log are reset for the new project.

## Repositories panel

The panel on the left lists every repository indexed into the active project.

**Resizing and collapsing** — drag the right edge of the panel to resize it. Double-click the edge to snap back to the default width. Clicking the collapse button shrinks it to a narrow icon rail; the repo icons remain visible as a quick-reference inventory.

**Selecting repositories** — clicking a row selects that repository and highlights its nodes in the graph. You can build a multi-repo selection:

- **Ctrl/Cmd + click** to toggle individual repositories in or out of the selection
- **Shift + click** to range-select from the last-selected item to the clicked one

A selection here also filters the **Pull Requests** section — only PRs from the selected repositories are shown.

**Per-repository actions** — hover a row and click `…` to open its action menu:

- **Re-index** — runs a fresh indexing job against the same URL and branch. Useful after pushing new commits.
- **Remove** — permanently deletes all indexed data for that repository (files, directories, functions, classes) from the project. Shared dependency nodes are left in place. The project is auto-saved after removal so it takes effect immediately for all users.
- **Open on GitHub/GitLab** — opens the source URL in a new tab.

## Sections

The title bar has five sections: **Graph**, **Chat**, **Activity**, **Pull Requests**, and **Settings**.

### Graph

The default view. The graph toolbar has pills (Filters, Discover, History) that open floating side panels — they don't occupy permanent space in the layout.

While in this section, the **Chat** button in the top-right opens the AI assistant as a side panel next to the graph. The chat panel is resizable — drag its left edge. Your conversation is preserved if you close the panel and reopen it.

### Chat

Gives the AI assistant the full width of the workspace. A **Graph** button in the top-right opens a resizable graph reference panel alongside the chat, so you can browse the graph while the conversation is active. The graph reference panel shows the same live graph as the Graph section — node selection and graph state are shared between the two.

Your conversation is not reset when you switch between the Graph and Chat sections. The same chat session continues across both.

### Activity

A log of indexing and import jobs for the current session. While a job is running you can:

- **Minimise** — hides the progress card from this view without stopping the job. The status bar at the bottom of the workspace still shows live progress.
- **Cancel** — stops the job. This option is disabled once the job has moved past the initial running phase and data is already being written to the graph.

The activity log is session-scoped and resets when you switch to a different project.

### Pull Requests

Shows pull requests fetched from the GitHub API for every GitHub repository in the project. The list updates automatically when you add or remove repositories.

Filtering works across the full PR list by default. If you select one or more repositories in the repos panel, the list narrows to those repositories only.

The search box matches against PR title, author name, PR number (e.g. `#42`), and repository name.

Clicking a PR opens a detail panel showing its description (rendered as Markdown), reviewer states, file-change statistics with a proportional diff bar, and CI check results.

### Settings

Rename the project or edit its description. Changes apply everywhere the project name appears — the sidebar, the title bar, and the AI assistant's context.

The **Danger zone** contains a delete action that removes the project's metadata and graph archive from Firebase Storage. Other users in the organisation will lose access immediately.

## AI assistant setup

The first time you open the chat (or after clearing credentials) you are shown a setup screen with two options:

**Use your OpenTrace account** — intended for a free monthly token allowance with no API key required. This option is not yet active; the button is a placeholder for an upcoming feature.

**Bring your own key** — connect a provider directly. Four providers are supported:

| Provider         | Key format                                          |
| ---------------- | --------------------------------------------------- |
| Google Gemini    | Starts with `AIza` — get one at aistudio.google.com |
| Anthropic Claude | Starts with `sk-ant-`                               |
| OpenAI           | Starts with `sk-`                                   |
| Local LLM        | Base URL of an Ollama or llama.cpp server           |

For the **Local LLM** option the URL field is pre-filled with your current hostname and port 11434 (Ollama's default). This means it works whether you are accessing the app from `localhost` or from another machine on the same network without you having to edit the URL.

All keys and URLs are stored only in your browser's `localStorage`. They are never transmitted to OpenTrace servers. Changes made in another browser tab — including clearing a key — are reflected immediately; the chat will return to the setup screen if valid credentials are no longer present.

## Saving

The project graph is held in memory and must be saved to persist across reloads.

**Auto-save** is enabled by default. It triggers automatically when an indexing or import job finishes — specifically at the point when all graph data has been written to the store, before slower background enrichment completes. This means the save is reliable even if enrichment is slow or interrupted.

You can disable auto-save from the dropdown on the Save button (the small chevron on its right side). With auto-save off, the status bar will show **Unsaved changes** after any job completes. With it on, that warning does not appear — the auto-save will take care of it.

The status bar at the bottom of the workspace shows the save state at all times: whether a save is in progress, when the last save completed, and whether it was triggered automatically or manually — for example, `Saved · 2 min ago (auto)`.
