# Slack

Connect OpenTrace to Slack to ask questions about your system architecture directly from your workspace.

## Overview

The Slack integration lets you start OpenTrace Chat conversations from Slack threads. Ask a question in Slack, and the AI responds with answers grounded in your knowledge graph — without leaving your messaging workflow.

## How It Works

1. Start or mention OpenTrace in a Slack thread
2. The AI reads the thread context to understand your question
3. OpenTrace queries your knowledge graph and responds in the thread
4. The conversation is also visible in OpenTrace Chat for further exploration

## Starting a Chat from Slack

Mention OpenTrace in any channel or thread where the integration is installed. Your message and the surrounding thread context are used to inform the response.

> @OpenTrace what services depend on the payment API?

The AI will reply in the same thread with an answer based on your architecture graph.

## Continuing Conversations

Each Slack thread maps to an OpenTrace conversation. Follow-up messages in the same thread maintain context, so you can ask progressively deeper questions:

> @OpenTrace what does checkout-api depend on?

> @OpenTrace which of those are databases?

> @OpenTrace what else connects to postgres-main?

## Viewing in OpenTrace

Conversations started from Slack also appear in the OpenTrace Chat sidebar. You can continue them in the dashboard if you want access to features like the artifact panel and graph visualization.

## Setup

To enable the Slack integration for your organization, contact your OpenTrace admin or visit the integrations page in the dashboard.
