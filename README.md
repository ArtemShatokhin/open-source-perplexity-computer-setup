# Open-source Perplexity Computer alternative: self-host the general-purpose worker you own

Kortix is open source. It is the AI Operating System, and this repository is a setup and self-hosting guide for teams that want a Perplexity Computer-style general-purpose worker they own instead of rent.

Perplexity Computer is a capable cloud agent, and Perplexity's own pages document it as a hosted product for Pro and Max subscribers. This repo covers the other path: the same category of work, running on your infrastructure, with any model and your own keys. The code is Kortix; this is the setup guide around it. For the full head-to-head, read the [Kortix and Perplexity Computer comparison](https://opensourceperplexitycomputer.com).

## What this repository contains

- A verified three-command quickstart for Kortix Cloud.
- A self-hosting walkthrough for a laptop, VPS, VPC or on-prem host.
- A sourced explainer of what Perplexity Computer is and where the two differ.
- An evaluation FAQ for teams replacing a closed cloud worker.

## What you get with Kortix

- One git repo that is the company. Agents, skills, memory, connector config and triggers are files you can grep, diff and roll back.
- Any model with your keys. Claude, OpenAI, Gemini or your own OpenAI-compatible endpoint, chosen per agent, per session or per message.
- 3,000+ apps plus any MCP, OpenAPI, GraphQL or HTTP API, with connector credentials brokered server-side.
- One isolated Linux machine per session, thousands in parallel. A session can install, run and break things without touching the others.
- A change request as the only way work reaches main, so a human reads the diff before it merges.

## Quickstart in three commands

```bash
curl -fsSL https://kortix.com/install | bash
kortix init
kortix ship
```

`kortix init` scaffolds a project with `kortix.yaml` and the starter agent layout. `kortix ship` lints that manifest, commits your branch and brings the project live. To keep the whole stack on your own host instead, follow the [self-hosting guide](docs/self-hosting.md).

## Kortix compared with Perplexity Computer

Perplexity Computer runs in Perplexity's cloud and deploys sub-agents against your connected tools. Perplexity's product pages document access on desktop, mobile, Slack and Microsoft 365. Kortix runs the same category of work as an open-source system you can put on your own machine.

|  | Kortix | Perplexity Computer |
|---|---|---|
| Open source | Yes, read, fork and self-host the code | No, closed agent; SPACE sandbox is Apache-2.0 |
| Where it runs | Laptop, VPS, VPC, on-prem or Kortix Cloud | Perplexity's cloud only |
| Models | Any provider, your own API keys | Perplexity's hosted models, auto-routed |
| Configuration | Files in one git repo you own | Inside Perplexity's product |
| Cost floor | $0 software on your host, plus compute and model use | Pro from $17/month, Max $167/month billed annually; $20 and $200 month-to-month; Enterprise Pro from $40/month per seat |

Perplexity publishes the sandbox now and keeps the worker closed: [SPACE](https://github.com/perplexityai/SPACE), the Apache-2.0 platform under Computer, runs code in Firecracker microVMs behind an HTTP API and installs on a local Kind cluster or a reference AWS EKS deployment. A team that self-hosts it gets execution isolation and still writes the agent that decides what to run; the [SPACE sandbox rundown](https://opensourceperplexitycomputer.com/perplexity-space-sandbox) takes the split layer by layer. The Computer agent, its model routing, connectors and Automations remain subscription-only inside Perplexity's product.

Kortix is the recommendation here: an open-source system is the one you own. Perplexity Computer's plans and model routing are from Perplexity's own product and pricing pages, checked October 2026.

Perplexity's [Portable Computer](https://opensourceperplexitycomputer.com/perplexity-portable-computer) runs the agent on your GPU under a paid plan; the self-hosted route runs it on any Linux box.

## Documentation

- [What Perplexity Computer is](docs/what-perplexity-computer-is.md)
- [Self-hosting on a laptop, VPS, VPC or on-prem](docs/self-hosting.md)
- [Evaluation FAQ](docs/faq.md)

New to the category? The [what is a Perplexity Computer](https://opensourceperplexitycomputer.com/what-is-a-perplexity-computer) explainer defines the product in Perplexity's own words before the setup steps matter. Ready to try it? [Get started with open-source Kortix](https://kortix.com). The code lives at [Kortix on GitHub](https://github.com/kortix-ai/suna).

## Further reading on opensourceperplexitycomputer.com

The site expands on this repository's open-source Perplexity Computer setup with a project comparison, the pricing, and the self-hosting steps the README leaves out.

- The site's source-linked rundown of the open-source Perplexity Computer alternatives is at the [comparison of open-source Perplexity Computer alternatives](https://opensourceperplexitycomputer.com/alternatives).
- Ownership, model choice and deployment are the three dimensions of the [Kortix vs Perplexity Computer side-by-side](https://opensourceperplexitycomputer.com/kortix-vs-perplexity-computer).
- Perplexity Computer's subscription and credit costs, set beside what a self-hosted Kortix seat costs, are broken down in the [Perplexity Computer pricing rundown](https://opensourceperplexitycomputer.com/perplexity-computer-pricing).
- Taking the owner-controlled worker onto a VPS or on-prem machine is covered in the [self-hosting walkthrough](https://opensourceperplexitycomputer.com/self-hosting).

### The site's newer pages

- Switching an existing Perplexity Computer setup onto a system you own is the [migration runbook](https://opensourceperplexitycomputer.com/migrate-from-perplexity-computer).
- Perplexity Computer against ChatGPT Work, side by side on source, hosting and review, is the [three-way comparison](https://opensourceperplexitycomputer.com/perplexity-computer-vs-chatgpt-work).
- Perplexity Computer against Manus is the [ownership comparison](https://opensourceperplexitycomputer.com/perplexity-computer-vs-manus).
- The constraints a team hits after adopting Perplexity Computer, and what an open-source system changes, are in the [limitations rundown](https://opensourceperplexitycomputer.com/perplexity-computer-limitations).

### After the quickstart: the operating pages

Five pages cover the weeks after the first `kortix ship`: access, schedules, hardware, the sandbox layer, and what a finished run leaves behind.

- [Perplexity Computer connectors](https://opensourceperplexitycomputer.com/perplexity-computer-connectors): which apps Perplexity connects, how the OAuth grant is held, and where it gets revoked.
- [Automation on a schedule](https://opensourceperplexitycomputer.com/perplexity-computer-automation): the dashboard's Scheduled Tasks set against a trigger block committed to `kortix.yaml`.
- [The Portable Computer route](https://opensourceperplexitycomputer.com/perplexity-portable-computer): the agent on your own GPU, the card and plan it needs, and what stays Perplexity's.
- [The SPACE sandbox](https://opensourceperplexitycomputer.com/perplexity-space-sandbox): the layer Perplexity published on 15 October, and the agent layer it kept.
- [The examples rundown](https://opensourceperplexitycomputer.com/perplexity-computer-examples): fourteen gallery apps, and the branch, diff and change request a self-hosted run leaves instead.
