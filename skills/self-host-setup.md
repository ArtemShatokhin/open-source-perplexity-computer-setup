# Skill: self-host-setup

How to stand up open-source Kortix on infrastructure this team controls and prove it
works.

## Steps

1. Install the CLI: `curl -fsSL https://kortix.com/install | bash`.
2. Start the stack: `kortix self-host start`.
3. Point the CLI at it: `kortix hosts use selfhost` (switch back with
   `kortix hosts use cloud`).
4. Configure the host: one domain with DNS records, one sandbox provider key,
   and the connectors the team needs.
5. Boot a session, run a real task, and merge the change request it opens.
6. Record the backup path and the upgrade command.

## Definition of done

A session runs on the team's own host, a real task lands as a reviewed
change, and the runbook in `docs/self-hosting.md` matches what was done.
