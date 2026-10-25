# Review rules

The review rules of vulpes-facility for haechi's reviewers, in every repository of the organization.\
A repository's own `REVIEW.md` wins where it conflicts with these rules,\
and these rules win over the repository's `CLAUDE.md` and `AGENTS.md`.\
Add a rule as a section under **Always check**.

## Review against intent

- Derive the intent from the PR description, the issues that it closes, and the commit messages.
- Report a requirement of the description that the diff does not implement, or implements wrongly.
- Report a commit message that claims a change the diff does not hold.
- Mention changes outside the stated scope in the summary.
- When there is no description, review the code alone, and say so in the summary.

## What blocks

`blocking` is only for a critical defect that the pull request introduces:\
logic that gives wrong results, a security vulnerability, data loss,\
or a crash or broken behavior in the repository's real use.\
Everything else is `non-blocking`, and the assignee decides whether to act on it.

## Always check

### Change history in files

A file's text MUST describe the current state; git history records how it changed.\
Report each of these as `nitpick (non-blocking)`:

- Comments or notes that narrate a change, such as "previously", "changed from", "removed", "no longer", "new:", or "(was X)".
- Commented-out code.
- Change logs inside source files.
- `_old`, `_new`, or `_v2` copies kept beside their replacement.

Files whose purpose is recording history, such as `CHANGELOG.md`, migrations, and decision records, are exempt.

### PR description

The PR description MUST follow the organization's template, `.github/pull_request_template.md` of the `.github` repository.\
Report each deviation with the location `description`.

| Rule | Finding |
| --- | --- |
| The headings are exactly `## Why`, `## What`, `## Verification`, and `## Related`, in this order, and stay in English whatever language the body uses. | `issue (non-blocking)` |
| Each section has content, and Verification states both what was verified and what was not. | `issue (non-blocking)` |
| Why and What hold no issue or pull request numbers; they appear as footnotes `[^name]` whose definitions sit between the `footnotes:start` and `footnotes:end` markers. | `nitpick (non-blocking)` |
| Related lists `- Closes #N` and `- Refs #N` lines, with no bare `#` left behind. | `nitpick (non-blocking)` |
| Each sentence is on its own line. | `nitpick (non-blocking)` |
| The template's guidance text is replaced, not left in place. | `nitpick (non-blocking)` |
