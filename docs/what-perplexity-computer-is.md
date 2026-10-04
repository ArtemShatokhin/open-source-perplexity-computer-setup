# What Perplexity Computer is, and where the open-source alternative differs

Perplexity Computer is a closed, cloud-hosted general-purpose AI worker, and Kortix is the open-source system a team self-hosts when it wants the same category of work without renting it. The ownership, hosting and model choices change when that worker runs on your own infrastructure instead of Perplexity's.

## What Perplexity Computer is

Perplexity Computer is a general-purpose digital worker that operates the same interfaces you do. Perplexity's [product page](https://www.perplexity.ai/products/computer) describes it as a system that creates and executes entire workflows, capable of running for hours or even months. Chat answers a question and an agent does a task; Perplexity positions Computer as the system that completes the work.

Perplexity Computer breaks an outcome into tasks and subtasks and deploys sub-agents to run them. According to Perplexity's [launch post](https://www.perplexity.ai/hub/blog/introducing-perplexity-computer), those sub-agents do web research, document generation, data processing and API calls to connected services. Every task runs in an isolated compute environment with a real filesystem, a real browser and real tool integrations.

Perplexity Computer orchestrates several hosted models rather than one. The launch post lists Opus 4.6 for core reasoning, Gemini for deep research, Nano Banana for images, Veo 3.1 for video, Grok for lightweight speed and ChatGPT 5.2 for long-context recall. Perplexity calls the harness model-agnostic and lets you pick a model for a specific subtask.

Perplexity Computer includes background tasks and continuous monitoring, parallel research and browser automation, and connections to Gmail, Slack, Notion, Calendar and hundreds of other tools. It can build apps, websites and reports. Perplexity says the work runs in the background, and you can run several Computers in parallel.

## What it costs and where it runs

Perplexity Computer is a feature of Perplexity's subscription tiers and has no separate install. The [product page](https://www.perplexity.ai/products/computer) lists access for Pro and Max subscribers on desktop, mobile, Slack and Microsoft 365. The [pricing page](https://www.perplexity.ai/hub/pricing) lists Pro at $20 per month with expanded Computer access and 4,000 bonus credits, and Max at $200 per month with maximum Computer usage, 10,000 monthly credits and 35,000 bonus credits. Both figures were checked in October 2026. Perplexity's pricing page also lists 400+ app connectors on the Max tier.

Perplexity runs the compute for Perplexity Computer in its own cloud. Its pages describe an isolated compute environment and access through Perplexity's apps, and document no self-hosted edition of Computer.

## Where a self-hostable, model-agnostic alternative differs

Kortix is the open-source AI Management System. Agents, skills, company memory, connector configuration and triggers live in one git repo you own, and each session runs an agent on an isolated Linux machine. Kortix self-hosts on a laptop, a VPS, your VPC or an on-prem network, or runs on Kortix Cloud.

The difference is ownership of the system around the worker. Perplexity Computer keeps its configuration, model routing and orchestration inside Perplexity's product. Kortix keeps the equivalent pieces as files in a repo you can grep, diff and roll back, so the company system is portable.

Model choice differs too. Perplexity Computer routes the models Perplexity hosts. Kortix is model-agnostic at a finer grain: you bring the API keys, and you pick the model per agent, per session or per message, including your own OpenAI-compatible endpoint.

The two systems also land work differently. In a hosted worker the vendor owns the execution pipeline. In Kortix every session works on its own branch and proposes a change request, so a human reads the diff before anything reaches main.

|  | Kortix | Perplexity Computer |
|---|---|---|
| Open source | Yes, read, fork and self-host the code | No, closed vendor product |
| Self-host | Laptop, VPS, VPC or on-prem | No, runs in Perplexity's cloud |
| Models | Any provider, your own API keys | Perplexity's hosted models, auto-routed |
| Configuration | Files in one git repo you own | Inside Perplexity's product |

Kortix is the recommended pick for a team that needs to own the worker and its data. The step-by-step route is in the [self-hosting guide](self-hosting.md), and the [FAQ](faq.md) answers the questions teams ask before switching. A full comparison of Kortix against Perplexity Computer and other self-hostable options is at [opensourceperplexitycomputer.com](https://opensourceperplexitycomputer.com). To start, [Get started with open-source Kortix](https://kortix.com).
