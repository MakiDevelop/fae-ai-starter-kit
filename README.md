# AI Workflow Starter Kit for Field Application Engineers

Two production-ready systems for FAEs working across multiple regions:

1. **Content Quality Pipeline** — an n8n workflow that runs your draft through Claude for refinement, Gemini for independent critique, automated scoring, and Slack notification for your final approval.

2. **Cross-Region Knowledge Base Architecture** — a two-layer design (structured case management + semantic intelligence) that turns years of multi-region field experience into a prediction engine.

## Quick Start

1. Open the [Setup Guide](https://kit.ranran.tw/)
2. Download [`llm-judge-workflow.json`](llm-judge-workflow.json) and import it into [n8n](https://n8n.io/)
3. Add your API keys (Claude, Gemini, Slack webhook)
4. Run your first content through the pipeline

## What's Inside

| File | Description |
|------|-------------|
| `guide.html` | Complete setup guide with architecture diagrams, data schema, and 3-phase deployment roadmap |
| `llm-judge-workflow.json` | n8n workflow — import directly into any n8n instance (self-hosted or cloud) |

## Content Pipeline Flow

```
Your Draft → Claude (refine) → Gemini (critique & score) → Evaluation Gate → Slack (you approve)
```

Gemini scores six dimensions: technical accuracy, clarity, audience fit, originality, actionability, and brand safety. Default pass threshold: 80/100.

## Knowledge Base Architecture

```
Layer 1: Case Management          Layer 2: Intelligence
┌─────────────────────────┐       ┌──────────────────────────┐
│  Notion  (cloud, collab) │       │  AnythingLLM (local, safe)│
│  or                      │──────▶│  or                      │
│  Obsidian (local, secure)│       │  n8n + Pinecone + Claude │
└─────────────────────────┘       └──────────────────────────┘
```

- **Notion** for de-identified enterprise cases and team collaboration
- **Obsidian + AnythingLLM Desktop** for military/classified content (100% local, no data leaves your machine)

## Requirements

- [n8n](https://n8n.io/) (Desktop, Docker, or Cloud)
- [Claude API key](https://console.anthropic.com/)
- [Gemini API key](https://aistudio.google.com/)
- Slack incoming webhook (optional, for notifications)

## License

MIT
