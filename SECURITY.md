# Security

Report vulnerabilities privately to **dev@swamplink.com** rather than opening a
public issue. If a repo has GitHub private vulnerability reporting enabled, that
works too and is preferred — it keeps the report attached to the code.

There is no formal SLA. These are one person's tools with public issue trackers,
not supported products. Reports will be acknowledged and fixed as promptly as
possible, and you will be credited in the release notes unless you ask not to be.

## Supported versions

Only the latest release of any project is supported. Each repo's `CHANGELOG.md`
says what that is.

## What is in scope

Most of these tools are read-only monitors that run on a machine you already
control, which shapes what counts as a vulnerability:

- **In scope:** anything that lets untrusted input reach a shell, write to a
  tree or registry the tool promises never to touch, exfiltrate session
  contents or tokens, or escalate beyond the invoking user. Transcript and
  session files are attacker-influenceable — a repo name, branch name, commit
  subject or agent task string can carry whatever someone put there, and a tool
  that renders or executes it unsafely is a real bug.
- **Out of scope:** anything that requires an attacker who already has your
  user account, and the fact that a monitoring tool displays data that is
  already on your disk.

## What these tools do and do not touch

Every dashboard here is read-only by construction: it reads session
transcripts, runs `gh` and read-only git plumbing, and probes localhost ports.
It does not write to a working tree, a registry, or a session. Where a single
exception exists it is off by default and armed by an explicit keypress, and
the repo's README says so.

If you find one of these tools writing somewhere it should not, that is a
security report, not a feature request — send it to the address above.
