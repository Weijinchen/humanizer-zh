# humanizer-zh

`humanizer-zh` is a Codex skill for rewriting Chinese prose so it reads less like generated text and more like careful human writing.

It is tailored for:

- textbook drafting
- paper drafting
- literature reviews
- research summaries
- long-form explanatory prose

## What it does

- removes translation-like phrasing
- reduces repetitive AI paragraph templates
- keeps terminology, citations, and claims stable
- distinguishes textbook mode from paper mode
- preserves academic restraint instead of turning everything into marketing copy

## Included files

- `SKILL.md`: main skill definition
- `references/academic-patterns.md`: common AI-like Chinese writing patterns and rewrites
- `references/discipline-guardrails.md`: accuracy rules for academic and technical prose

## Install

For Codex, place this folder in a skills directory as:

`humanizer-zh/`

Typical locations:

- `~/.codex/skills/humanizer-zh`
- a project-local `skills/humanizer-zh`

Then call it in requests about rewriting, polishing, or AI-trace reduction in Chinese writing.

## Example prompts

- `请用 humanizer-zh 改写这段教材，让表达更自然，但保留术语和结构。`
- `请用 humanizer-zh 处理这段论文摘要，降低翻译腔，不要改引文标记。`
- `请用 humanizer-zh 先指出这段文字的 AI 痕迹，再给我一个重写版。`

## Important boundary

This skill is for improving writing quality and reducing formulaic AI traces. It should not be used to fabricate evidence, hide misconduct, or falsify authorship claims.
