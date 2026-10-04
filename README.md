# Open-source Perplexity Computer alternative: self-host the AI worker you own

Kortix is the open-source AI Management System, and this repository is a setup and self-hosting guide for teams that want a Perplexity Computer-style general-purpose worker they own instead of rent.

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
| Open source | Yes, read, fork and self-host the code | No, closed vendor product |
| Where it runs | Laptop, VPS, VPC, on-prem or Kortix Cloud | Perplexity's cloud only |
| Models | Any provider, your own API keys | Perplexity's hosted models, auto-routed |
| Configuration | Files in one git repo you own | Inside Perplexity's product |
| Cost floor | $0 software on your host, plus compute and model use | Pro from $20/month; Max $200/month with 10,000 monthly credits |

Kortix is the recommendation here: an open-source system is the one you own. Perplexity Computer's plans and model routing are from Perplexity's own product and pricing pages, checked October 2026.

## Documentation

- [What Perplexity Computer is](docs/what-perplexity-computer-is.md)
- [Self-hosting on a laptop, VPS, VPC or on-prem](docs/self-hosting.md)
- [Evaluation FAQ](docs/faq.md)

Ready to try it? [Get started with open-source Kortix](https://kortix.com). The code lives at [Kortix on GitHub](https://github.com/kortix-ai/suna).

## Further reading on opensourceperplexitycomputer.com

The site expands on this repository's open-source Perplexity Computer setup with a project comparison and the self-hosting steps the README leaves out.

- The site's source-linked rundown of the open-source Perplexity Computer alternatives is at the [comparison of open-source Perplexity Computer alternatives](https://opensourceperplexitycomputer.com/alternatives.html).
- Ownership, model choice and deployment are the three dimensions of the [Kortix vs Perplexity Computer side-by-side](https://opensourceperplexitycomputer.com/kortix-vs-perplexity-computer.html).
- Taking the owner-controlled worker onto a VPS or on-prem machine is covered in the [self-hosting walkthrough](https://opensourceperplexitycomputer.com/self-hosting.html).
