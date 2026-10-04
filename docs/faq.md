# Open-source Perplexity Computer FAQ

Kortix is the open-source AI Management System, and teams evaluating it as an alternative to Perplexity Computer ask these questions first.

## Do I need a Perplexity subscription to run Kortix?

No. Kortix is a separate, open-source system, so nothing in this repository depends on a Perplexity account. You install the Kortix CLI, run it against your own host or Kortix Cloud, and bring your own model keys or use the Kortix gateway. Perplexity's subscription buys access to Perplexity Computer inside Perplexity's apps.

## Is Perplexity Computer open source?

No. Perplexity Computer is a closed, cloud-hosted product available to Perplexity's Pro and Max subscribers, and Perplexity's pages document no self-hosted edition. Kortix is open source and self-hostable, so you can read the code, fork it and run it on your own infrastructure. The choice is between renting a hosted worker and owning the system around yours.

## Which models can Kortix run?

Kortix is model-agnostic. You can run Claude, OpenAI, Gemini or your own OpenAI-compatible endpoint, and choose the model per agent, per session or per message. You supply your own API keys, or use your existing ChatGPT subscription, or the Kortix gateway. Perplexity Computer routes the models Perplexity hosts instead.

## Where does my data live?

On your infrastructure when you self-host, and in your project when you use Kortix Cloud. Each session runs on an isolated Linux machine, connector credentials are brokered server-side so the raw key never enters the sandbox, and secrets are encrypted at rest and injected at runtime. Agents, skills and memory are files in your own git repo.

## How is Kortix different from a chatbot?

A chatbot returns an answer in a thread. Kortix runs agents on real machines that can install, run and break things, then land finished work as a change request a human reviews as a diff. The work reaches main only when you merge it, which makes agent output reviewable rather than automatic.

## What does Kortix cost?

Self-hosting is free software: you pay only for the compute you run and any model API you choose. On Kortix Cloud, Free is $0 and includes 200 credits / month for sandbox compute; Team is $40 / seat / mo and includes 2,500 credits / month per seat, pooled. Kortix lists Enterprise pricing on request. See [Kortix pricing](https://kortix.com/pricing) for the current figures.

## Can I run Kortix fully offline?

Not from the default install. `kortix self-host start` pulls its images from Docker Hub, so a default self-hosted instance is self-hosted rather than network-isolated. The [self-hosting guide](self-hosting.md) notes this caveat, and an evaluation that must run disconnected needs its own image registry in front of it.

## Can I keep using Slack and Microsoft Teams?

Yes. You can start and steer Kortix sessions from the web app, the CLI, the API or Slack, with Microsoft Teams available behind an operator switch. Cron jobs and signed webhooks can start sessions with nobody asking. Your team keeps working where it already does, and the agent output still arrives as a change request.

A full comparison of Kortix against Perplexity Computer and other self-hostable options is at [opensourceperplexitycomputer.com](https://opensourceperplexitycomputer.com). To try the managed cloud first, [Get started with open-source Kortix](https://kortix.com).
