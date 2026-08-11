# Contributing

This is the default that applies to any of my repos without its own
`CONTRIBUTING.md`. **A repo-level file always wins** — check there first, since
it will carry the actual test command.

Contributions are welcome, including the ones that are just "this is wrong."

## Before a big change, open an issue

Small fixes — a bug, a typo, a wrong number in the docs — go straight to a pull
request. For anything larger, open an issue first and say what you are trying to
do. These tools are deliberately small, and the most common reason a PR gets
turned down is that it is good work aimed at a feature the project does not want
to have. An issue costs you five minutes; a rejected PR costs you an afternoon.

## What most of these projects promise

Several of the tools here are single-file, standard-library-only Python that has
to run on whatever interpreter is already on the box. Where a repo says that, it
means it:

- **No new dependencies.** A dependency is one more thing that can be missing at
  7am on a machine you are already debugging. CI enforces this with an
  import check on some repos.
- **Read-only by construction.** If a change makes a monitoring tool write
  somewhere, it needs a much better reason than convenience, and it needs to be
  off by default.
- **A missing data source degrades to a labelled gap, never an error.** A
  dashboard that dies because `gh` is not installed has chosen the worst
  available behaviour.

## Tests

Run the repo's test suite before opening a PR. Unless its own `CONTRIBUTING.md`
says otherwise, that is:

```bash
python -m unittest discover -s tests -t . -v
```

That is the same command CI runs, across the Python versions and platforms in
that repo's `ci.yml`.

## Pull requests

- PRs merge **squash-only**, and the PR title becomes the commit message. Title
  it as a [conventional commit](https://www.conventionalcommits.org/) —
  `feat:`, `fix:`, `docs:`, `chore:`, `ci:`, `test:`. Some repos lint this and
  will fail the PR on a title that does not match.
- Update the `CHANGELOG.md` entry in the same commit as the change, not
  afterwards.
- Do not bump versions or add tags by hand. Releases are cut by the repo's own
  release workflow.

## Numbers and claims

Some of these projects exist specifically to make a figure defensible. In those,
**every number traces to a primary source, cited inline, with the version or
year it applies to.** A plausible number without a source is a defect there, not
a rough draft — if you cannot source it, leave the claim out.

## Security

Do not open a public issue for a vulnerability. See
[SECURITY.md](SECURITY.md) — it goes to dev@swamplink.com.
