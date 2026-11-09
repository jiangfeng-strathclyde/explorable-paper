# Explorable Paper

Turn a scholarly paper into an evidence-linked interactive HTML exploration.

Explorable Paper is an agent skill for building interfaces that help readers
test their understanding of a paper: change a parameter, inspect a mechanism,
follow an algorithm, compare evidence, and see where a claim stops applying.
It is not a decorative paper summary or a generic paper website.

[Try the movable-antenna example](https://jiangfeng-strathclyde.github.io/Athena/examples/antenna-direction.html)

## What the skill produces

- an offline-first HTML artifact;
- a claim-to-evidence map with precise source locators;
- interactions selected for explanatory value;
- explicit labels for reported evidence, data exploration, teaching models,
  and method execution;
- separate structural, numerical, browser, and research-reproduction checks.

The default artifact is a self-contained HTML file that can open from
`file://` without a server, CDN, telemetry, or network request.

## Install

Install this repository as a skill using the mechanism supported by your agent,
or copy the repository into its skills directory. The installable entry point
is [`SKILL.md`](SKILL.md); no Python package installation is required.

For Codex, place the folder at:

```text
~/.codex/skills/explorable-paper/
```

Then ask:

```text
Use $explorable-paper to turn this paper into an offline, evidence-linked
interactive HTML exploration.
```

Other agents can use the same folder when their host supports `SKILL.md` or an
equivalent Agent Skills convention. The generated artifact itself is ordinary
HTML and does not depend on a particular agent.

## Modes

- **Create** an explorable article from a paper and its available materials.
- **Audit** an existing explorable article without silently redesigning it.
- **Extend** a bounded module while preserving verified behavior and sources.

Read [`SKILL.md`](SKILL.md) for the complete workflow and evidence rules.

## Validate an artifact

The bundled preflight checks common packaging failures:

```bash
python scripts/validate_explorable.py path/to/output.html
```

Run the repository tests with:

```bash
python -m unittest discover -s tests -p "test_*.py"
```

The validator does not establish scientific correctness or reproduction. A
real delivery also requires source review, numerical checks, and browser
interaction testing.

## Example

[`examples/antenna-direction.html`](examples/antenna-direction.html) is a
self-contained exploration of movable-antenna channel geometry and position
optimization. It is a design case study, not a universal visual template.

The source paper PDF, third-party archives, unpublished experiment outputs,
and generated screenshots are intentionally excluded.

## Relationship to Athena

This standalone repository and the
[`explorable-paper` skill in Athena](https://github.com/jiangfeng-strathclyde/Athena/tree/main/skills/explorable-paper)
contain the same skill. Athena provides the integrated research-skill catalog;
this repository provides a focused installation and contribution surface.
Changes should be synchronized deliberately and recorded in both repositories.

## License

MIT. See [`LICENSE`](LICENSE).
