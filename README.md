# Research Like a Clown

![Research Like a Clown](assets/banner.svg)

[![Claude Code](https://img.shields.io/badge/Claude_Code-Skill-d97757)](https://code.claude.com/docs/en/skills) [![Patterns](https://img.shields.io/badge/patterns-28-326778)](references/patterns.md) [![Snapshot](https://img.shields.io/badge/snapshot-2026--09--26-526174)](references/evidence.json) [![GitHub stars](https://img.shields.io/github/stars/ShipOfShame/Research-Like-a-Clown?style=flat)](https://github.com/ShipOfShame/Research-Like-a-Clown/stargazers)


**Paper-derived error patterns as a writing skill, designed first for Claude Code.**

[Quick start](#install-in-claude-code) · [Pattern catalog](references/patterns.md) · [Source records](references/evidence.json) · [Contributing](CONTRIBUTING.md) · [简体中文](README.zh-CN.md)

The initial case material comes from review records of papers coauthored by **Ironieser (Sixun Dong)**. Research Like a Clown distills the recorded paper and code issues into a writing skill that deliberately generates passages containing those error mechanisms. Original references and their scope are retained for checking each pattern.

## What is included

| Area | Representative patterns |
| --- | --- |
| Results and metrics | Invalid aggregates, switched metric meanings, scores assigned to the wrong condition |
| Mathematical definitions | Identity state transitions, incompatible function domains, incorrect denominators |
| Evaluation | Split overlap, test-guided selection, normalization that removes errors |
| Implementation and artifacts | Missing evaluator inputs, code/specification mismatches, unexecuted revisions |
| Reporting and availability | Inconsistent model identifiers, vocabulary/sequence confusion, incomplete materials |

The **2026-09-26 review snapshot** contains **33 issue records across 19 papers**, distilled here into **28 patterns**. Repeated mechanisms are grouped; one record containing two different defects maps to two patterns. This is coverage of the supplied records, not a claim to enumerate all errors in those papers.

Patterns cover inconsistent aggregates and metric labels, invalid mathematical definitions, incompatible method classifications, code/specification mismatches, evaluation leakage, missing evaluator inputs, inaccurate artifact provenance, and discrepancies in material availability. Implementation patterns produce paired descriptions and pseudocode when prose alone would not express the defect.

The package preserves the review records and their original source links, versions, dates, and scope limits. Packaging did not independently re-check every external source or reproduce experiments. Records describe paper or repository observations; they do not establish personal responsibility or misconduct. Generated passages are constructed text, not additional evidence about the papers.

## Install in Claude Code

For a first-time personal installation:

```sh
mkdir -p ~/.claude/skills
git clone https://github.com/ShipOfShame/Research-Like-a-Clown.git ~/.claude/skills/research-like-a-clown
```

For installation in one project, run this from that project's root instead:

```sh
mkdir -p .claude/skills
git clone https://github.com/ShipOfShame/Research-Like-a-Clown.git .claude/skills/research-like-a-clown
```

Choose one location. If the destination already exists, inspect that installation before updating it. When installing from an extracted ZIP, copy the folder to the same destination and retain `references`.

Start a new Claude Code session and invoke:

```text
/research-like-a-clown Use P02 to write a short results passage with a constructed table about document retrieval. Write in English.
```

More examples:

```text
/research-like-a-clown Use P16 to write a feature-selection transition with symbolic sets.
/research-like-a-clown Use P25 to write a visual evaluation method and include the judge input payload.
/research-like-a-clown Use P26 to write a generation-log example with prompts P0, P1 and artifact I0. Put the source mapping in a separate response afterward.
```

See the [pattern index](references/patterns.md) for all IDs. The default is one compatible pattern, a short passage, and the language of your request. Ask explicitly to combine patterns. Unsupported mechanisms are declined rather than invented.

Generated passages omit diagnoses and correction advice. Symbolic or hypothetical premises distinguish constructed quantities from claims that experiments actually ran. This is not a tool for inserting defects into authentic research or submitting invented findings.

Claude Code may also select the skill when a request matches its description. Ordinary paper writing is excluded by that description. This package needs no hooks, MCP server, API key, dependency installation, network access, or execution of research code. Installation and invocation follow the [official Claude Code skills documentation](https://code.claude.com/docs/en/skills).

## Files

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Generation instructions |
| [Pattern catalog](references/patterns.md) | 28 mechanisms and their source mappings |
| [Evidence snapshot](references/evidence.json) | 33 dated review records |
| [Contributing](CONTRIBUTING.md) | Pattern and source updates |
| [中文说明](README.zh-CN.md) | Chinese installation and usage guide |

## Provenance and maintenance

The [evidence snapshot](references/evidence.json) records the source database URL, SHA-256 digest, review date, and all 33 source records. Its E-number identifiers are local stable references for this package. Each catalog entry explains the mechanism and maps it to those records.

When a source changes or is corrected, check the specific version and update the corresponding scope and pattern before issuing a revised package. Preserve historical dates; do not describe a reviewed snapshot as the current release without checking it.

## Contributions

Source corrections, scoped pattern additions, and usability improvements are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) or [open a source-update issue](https://github.com/ShipOfShame/Research-Like-a-Clown/issues/new?template=source-update.md).
