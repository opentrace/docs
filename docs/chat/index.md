# Chat

OpenTrace Chat is a built-in AI assistant that answers questions about your system architecture directly in the OpenTrace dashboard. No external tools or MCP configuration needed — just open a conversation and ask.

## Getting Started

1. Log in to your OpenTrace dashboard
2. Click **Chat** in the sidebar navigation
3. Start a new conversation and ask a question about your system

!!! tip
    If you don't see Chat in the sidebar, the feature may not yet be enabled for your organization. Contact your admin or reach out to support.

## Conversations

Chat organizes your interactions into **conversations**. Each conversation maintains its own context, so you can have separate threads for different topics.

### Creating a Conversation

Click the **New Chat** button in the chat sidebar to start a fresh conversation. Your conversation will be automatically titled based on your first message.

### Switching Between Conversations

The chat sidebar shows all your conversations. Click any conversation to switch to it. Your message history and context are preserved.

### Deleting Conversations

To keep your conversation list manageable, you can delete conversations you no longer need. Note that deleting a conversation permanently removes it along with all its messages.

## Asking Questions

Chat has access to your full OpenTrace knowledge graph. You can ask the same types of questions you'd ask through any MCP-connected AI assistant:

| Category | Example |
|----------|---------|
| **Discovery** | "What services exist in my system?" |
| **Dependencies** | "What does the checkout service depend on?" |
| **Impact Analysis** | "What breaks if the database goes down?" |
| **Connections** | "How does the frontend connect to payments?" |
| **Investigations** | "Help me debug why orders are slow" |

## Understanding Responses

Chat responses include several elements beyond plain text.

### Tool Calls

When the AI queries your knowledge graph, you'll see **tool call indicators** showing which tools were used and what data was retrieved. Click on a tool call to expand its details and see the raw results.

### Artifacts

Responses may include **artifact chips** — clickable references to nodes in your knowledge graph. These appear as inline links within the response text.

Clicking an artifact chip opens the **Artifact Panel**, which displays a subgraph visualization centered on that node. This lets you visually explore the component and its immediate connections without leaving the chat.

### Markdown Formatting

Responses are rendered with full markdown support including code blocks, tables, and lists.

## Tips for Effective Questions

**Be specific about services and components:**

> "What does order-service depend on?" works better than "Tell me about dependencies"

**Use the actual names from your system:**

> Use "user-auth-service" if that's the name in your graph, not just "auth"

**Ask follow-up questions to drill deeper:**

> Start with "What services are involved in checkout?" then follow up with "How does checkout-api connect to the database?"

## Chat vs. MCP Integrations

OpenTrace offers two ways to interact with your architecture knowledge:

| | Chat | MCP Integrations |
|---|------|-----------------|
| **Where** | OpenTrace dashboard | Your existing AI tools (Claude, Copilot, etc.) |
| **Setup** | None — built in | Requires MCP configuration and API token |
| **Best for** | Quick exploration, visual graph browsing | Deep coding sessions, IDE workflows |
| **Graph visualization** | Inline artifact panel | Depends on the AI tool |

Both approaches query the same knowledge graph and support the same types of questions. Choose whichever fits your workflow.

## Chat from Slack

You can also start OpenTrace Chat conversations directly from Slack. See the [Slack integration](slack.md) page for details.
