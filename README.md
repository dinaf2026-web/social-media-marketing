# social-media-marketing

A Claude skill for organic social-media strategy and platform-native content, built around a
claim-safety gate rather than a tone guide.

The skill turns a short request such as "market this product on Instagram" into a brief, a source
ledger, a strategy, a calendar, and finished copy. What makes it different from a prompt is the
gate it runs before anything external-facing is approved. That gate separates two questions that
marketing copy usually merges: where a statement came from, and whether the exact claim being made
is supported. A brand guide can tell you what the brand says. It cannot prove a health claim.

## What it refuses

- ingredient evidence used as finished-product evidence
- laboratory or animal research used as proof of a human outcome
- preliminary or observational research used as proof of causation
- research on one dose, formulation, or population used as proof for another
- a general disclaimer used to keep a headline that overstates the evidence
- a fabricated customer, quote, review, rating, endorsement, or before-and-after result
- invented percentages, survey results, audience sizes, savings, or timelines

It also names a check that could not be run instead of reasoning around it.

## Install

Add the catalog once, then install from it.

```
/plugin marketplace add dinaf2026-web/dina-skills
/plugin install social-media-marketing@dina-skills
```

## Layout

```
skills/social-media-marketing/
  SKILL.md                          the workflow and the strategy defaults
  references/claim-safety.md        the gate: source status, claim status, evidence fit
  references/platform-playbook.md   per-platform creative defaults, search wording, accessibility
  references/output-templates.md    strategy, calendar, audit, competitor, and script templates
  agents/openai.yaml                manifest for the OpenAI surfaces
  assets/icon.svg
```

The skill is usable on OpenAI surfaces through `agents/openai.yaml` and in Claude through the
plugin manifest in `.claude-plugin/`. This repository is a plugin, not a marketplace, so it
carries no `marketplace.json`. Adding its URL as a marketplace will not work. Install it from the
`dina-skills` catalog instead.

## Credits

Written by Dina Farhat. The first draft of the skill files was produced with OpenAI Codex in
August 2026 and revised there the same day. The claim-safety and source-discipline rules were
reviewed and edited afterwards in Claude Code, which collapsed a duplicated source-status
taxonomy into the gate file and added the rule covering a check that could not be run.

Nothing in this repository was adapted from a third-party project, so there is no `NOTICES.md`.

## License

MIT, see [LICENSE](LICENSE).
