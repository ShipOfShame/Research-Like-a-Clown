# Research Like a Clown

**Paper-derived error patterns as a writing skill, designed first for Claude Code.**

[简体中文](README.zh-CN.md)

The initial case material comes from review records of papers coauthored by **Ironieser (Sixun Dong)**. Research Like a Clown distills the recorded paper and code issues into a writing skill that deliberately generates passages containing those error mechanisms. Original references and their scope are retained for checking each pattern.

## What is included

The **2026-09-26 review snapshot** contains **33 issue records across 19 papers**, distilled here into **28 patterns**. Repeated mechanisms are grouped; one record containing two different defects maps to two patterns. This is coverage of the supplied records, not a claim to enumerate all errors in those papers.

Patterns cover inconsistent aggregates and metric labels, invalid mathematical definitions, incompatible method classifications, code/specification mismatches, evaluation leakage, missing evaluator inputs, inaccurate artifact provenance, and discrepancies in material availability. Implementation patterns produce paired descriptions and pseudocode when prose alone would not express the defect.

The package preserves the review records and their original source links, versions, dates, and scope limits. Packaging did not independently re-check every external source or reproduce experiments. Records describe paper or repository observations; they do not establish personal responsibility or misconduct. Generated passages are constructed text, not additional evidence about the papers.

## Install in Claude Code

Download and extract the package. Copy the **entire `research-like-a-clown` folder**, including `references`, to either:

- `~/.claude/skills/research-like-a-clown/` for your personal installation.
- `.claude/skills/research-like-a-clown/` inside one project for project-local use.

The resulting path must end with `research-like-a-clown/SKILL.md`, without an extra nested folder. Check an existing destination before copying so you do not overwrite an installation unintentionally.

From a directory containing the extracted folder, a first-time personal installation can use:

```sh
mkdir -p ~/.claude/skills
cp -R research-like-a-clown ~/.claude/skills/
```

Start a new Claude Code session and invoke:

```text
/research-like-a-clown Use P02 to write a short results passage with a constructed table about document retrieval. Write in English.
```

More examples:

```text
/research-like-a-clown Use P16 to write a feature-selection transition with symbolic sets.
/research-like-a-clown 用 P25 写一段视觉评估方法，附上评估器收到的输入结构。
/research-like-a-clown Use P26 to write a generation-log example with prompts P0, P1 and artifact I0. Put the source mapping in a separate response afterward.
```

See the [pattern index](references/patterns.md) for all IDs. The default is one compatible pattern, a short passage, and the language of your request. Ask explicitly to combine patterns. Unsupported mechanisms are declined rather than invented.

Generated passages omit diagnoses and correction advice. Symbolic or hypothetical premises distinguish constructed quantities from claims that experiments actually ran. This is not a tool for inserting defects into authentic research or submitting invented findings.

Claude Code may also select the skill when a request matches its description. Ordinary paper writing is excluded by that description. This package needs no hooks, MCP server, API key, dependency installation, network access, or execution of research code. Installation and invocation follow the [official Claude Code skills documentation](https://code.claude.com/docs/en/skills).

## Files

```text
research-like-a-clown/
├── README.md
├── README.zh-CN.md
├── SKILL.md
└── references/
    ├── patterns.md
    └── evidence.json
```

## Provenance and maintenance

The [evidence snapshot](references/evidence.json) records the source database URL, SHA-256 digest, review date, and all 33 source records. Its E-number identifiers are local stable references for this package. Each catalog entry explains the mechanism and maps it to those records.

When a source changes or is corrected, check the specific version and update the corresponding scope and pattern before issuing a revised package. Preserve historical dates; do not describe a reviewed snapshot as the current release without checking it.
