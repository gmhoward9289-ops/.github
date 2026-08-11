<!--
The PR title becomes the squash commit message. Make it a conventional
commit: feat: / fix: / docs: / chore: / ci: / test: — some repos lint this
and will fail the PR on a title that does not match.
-->

## What this changes

<!-- One or two sentences. What is different after this lands. -->

## Why

<!--
The problem, not the patch. If there is an issue, link it: "Closes #123".
If this is a bug fix, say what the wrong behaviour was — a reader six months
from now needs that more than the diff.
-->

## How it was verified

<!--
What you actually ran, and what you saw. "CI is green" is not verification of
a behaviour change; it is verification that nothing else broke.
-->

## Checklist

- [ ] Tests pass locally (`python -m unittest discover -s tests -t . -v`, unless the repo says otherwise)
- [ ] No new runtime dependency, or the PR body says why one is warranted
- [ ] Nothing here makes a read-only tool write to a tree, a registry, or a session
- [ ] `CHANGELOG.md` updated in this same commit, if the repo keeps one
- [ ] Version numbers and tags left alone — releases are cut by the release workflow
- [ ] Any new number in the docs cites its source
