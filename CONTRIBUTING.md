# Contributing

Contributions should improve a documented error pattern, its source mapping, or the skill's usability.

## Propose a pattern or source correction

Open an issue with the paper or repository URL, exact version or commit, relevant location, and a concise explanation. Include a minimal symbolic or arithmetic example when it helps establish the mechanism. For conditional code paths, describe the required input or configuration. Distinguish a publication claim from behavior in a released implementation.

Use the source-update issue template for corrections, changed material availability, or repaired implementations. Keep the historical observation dated and identify the replacement source. Do not submit personal information, speculation about motives, or generated passages as evidence about real authors.

## Change the skill

Keep `SKILL.md` short. Put mechanisms in `references/patterns.md` and supporting records in `references/evidence.json`. Preserve existing P and E identifiers; add new identifiers rather than renumbering old ones. Every pattern needs a source mapping and a concrete construction constraint.

Update both READMEs when changing installation or usage. Check relative links, pattern IDs, and the documented invocation. Report whether a change was inspected structurally or actually tried in Claude Code.

Keep maintainer information and local environment details out of public files. Review commit author details before publishing. Do not include credentials, local paths, conversation logs, or unrelated datasets.
