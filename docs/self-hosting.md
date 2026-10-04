# Self-hosting open-source Kortix on a laptop, VPS, VPC or on-prem

Kortix is the open-source AI Management System, and you can run the whole platform on hardware you control: a laptop for evaluation, a VPS, your own VPC or an on-prem host. The install needs the CLI, DNS records for your domain and a sandbox provider key, and the backup paths matter once you go past evaluation.

## What self-hosting runs

Kortix runs as one Docker Compose stack that contains the frontend, the API, the LLM gateway and the Supabase distribution. The agent sessions do not run inside that stack. They run on a separate sandbox provider, and the default is Daytona, with Platinum and E2B also supported. You configure the provider key during setup. The [self-hosting docs](https://kortix.com/docs/host) describe the full architecture.

## Install the CLI

The CLI is a prebuilt binary for macOS and Linux, and Windows is not supported.

```bash
curl -fsSL https://kortix.com/install | bash
```

## Prepare DNS, then initialize

For a domain-based install, create an A or AAAA record for your domain and for `api.<domain>`, both pointing at the box's IP. Open ports 80 and 443 so the bundled Caddy proxy can issue a TLS certificate. Then initialize the instance:

```bash
kortix self-host init --domain kortix.example.com
```

To try Kortix with no domain, initialize with a Cloudflare tunnel instead:

```bash
kortix self-host init --tunnel cloudflare
```

The tunnel URL changes on every restart, so use tunnel mode for evaluation rather than production.

## Start the stack

```bash
kortix self-host start
```

While it starts, `kortix self-host status`, the logs and `kortix self-host doctor` report what is happening. When the stack is up, run the interactive configuration to set the sandbox provider key and, optionally, a managed-git token:

```bash
kortix self-host configure
```

On a bare Linux box, the docs also offer a one-shot bootstrap script that installs Docker, installs the CLI and starts the stack in one command.

## Switch the CLI to your instance

The Kortix CLI stores auth per host. A self-hosted instance is the `selfhost` host, and you move between it and Kortix Cloud with one command each way:

```bash
kortix hosts use selfhost   # run against your own instance
kortix hosts use cloud      # switch back to Kortix Cloud
```

Sign in to the host, pick an account and a project, then open sessions as usual. `kortix hosts ls` shows every configured host and its auth state.

## Updates, backups and the offline caveat

Every self-hosted instance updates itself automatically. To pin a version instead, run `kortix self-host update --tag 0.9.84`, and turn the automatic updater off when you want full control.

Kortix has no separate backup system. Each instance stores its data under `~/.config/kortix/self-host/<instance>/`: the Postgres database in `volumes/db/data`, file storage in `volumes/storage`, and every secret and signing key in the instance's `.env` file. Back up all three before a destructive command.

`kortix self-host start` pulls its images from Docker Hub. That makes this a self-hosted install rather than a disconnected one, which matters if your evaluation requires a network-isolated host.

## Licence

Kortix is open source (Elastic License 2.0) — self-host, read and modify the code. The source is at [Kortix on GitHub](https://github.com/kortix-ai/suna).

To start with the managed cloud instead, [Get started with open-source Kortix](https://kortix.com).
