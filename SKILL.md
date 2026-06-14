---
name: humanizer-zh
description: Reduce visible AI-generation patterns in Chinese textbook drafts, academic prose, research summaries, and long-form nonfiction while preserving facts, citations, terminology, and the author's actual claims. Use when the user asks to "去 AI 味", "降低 AIGC 痕迹", "改得更像教材/论文/人写的", "减少翻译腔", or wants Chinese prose rewritten into natural, disciplined, publication-ready language.
---

# humanizer-zh

## Purpose

This skill rewrites Chinese prose so it reads like careful human writing instead of model-shaped output.

In practice, one recurring source of visible "AI flavor" is Chinese prose built on an English sentence skeleton: the grammar is legal, but the verbs, connectors, and paragraph cadence feel translated rather than written.

Its main use cases are:

- textbook drafting and chapter polishing
- paper drafting and revision
- literature review, introduction, discussion, and conclusion cleanup
- research summaries, teaching notes, commentary, and long-form explanatory prose

The goal is not to "fool detectors". The goal is to remove formulaic AI traces while preserving accuracy, traceability, and the author's real meaning.

## Non-Negotiables

1. Do not invent facts, data, experiments, references, quotations, policies, or citations.
2. Do not turn cautious claims into strong claims.
3. Do not remove necessary academic hedging when evidence is limited.
4. Do not change technical terms that have established usage unless the user asks.
5. Do not rewrite away structure that is required by the genre, such as definitions in textbooks or argument-evidence structure in papers.
6. If the source text contains placeholder citations, keep them as placeholders instead of fabricating bibliographic details.

## Default Workflow

1. Identify the genre first.
   Decide whether the text is a textbook chapter, lecture note, journal-style paper, thesis section, grant narrative, review article, or general nonfiction.
2. Identify the writing problem second.
   Distinguish between light polishing, deep rewriting, structural repair, or "explain why this sounds like AI".
3. Lock down what must not move.
   Preserve facts, chronology, citations, terminology, variable names, formulas, section logic, and explicit claims.
4. Remove the most visible AI patterns first.
   Prioritize translation-like syntax, list inflation, sloganized conclusions, repeated contrast frames, empty abstraction, and over-smoothed paragraph rhythm.
5. Repair sentence rhythm and paragraph function.
   Make each paragraph do one job: define, explain, compare, qualify, exemplify, transition, or conclude.
6. Run a final read-through for Chinese prose cadence.
   The text should read as if it was drafted directly in Chinese, not translated or assembled from prompts.

## Core Rules

### 1. Remove translation-like Chinese

- Cut phrases such as "对于……来说", "基于……", "围绕……展开", "使得……得以……" when simpler Chinese works.
- Avoid obvious English-to-Chinese sentence molds.
- Do not default to "不是……而是……" or "不仅……还……" unless the contrast is genuinely sharp.

### 2. Replace empty abstraction with mechanism

- Words like "赋能", "重塑", "颠覆", "深刻改变", "全新篇章" usually need concrete explanation or deletion.
- Replace vague evaluation with specific action, condition, scope, cost, or consequence.
- Prefer one precise claim over three inflated ones.

### 3. Break mechanical structure

- Do not make every paragraph look like "definition -> three points -> elevated conclusion".
- Reduce repeated "首先/其次/最后", "值得注意的是", "与此同时", "从某种意义上说".
- Convert forced lists back into prose when the content is narrative rather than tabular.

### 4. Restore human sentence rhythm

- Mix short and long sentences naturally.
- Give sentences clear subjects and actions.
- Do not end every paragraph with a slogan, a moral, or a grand prediction.
- Let some paragraphs stop after making a precise point.

### 5. Keep the article on one line of thought

- The opening question and closing answer must match.
- Remove or merge paragraphs that do not advance the central line.
- Do not introduce a larger "era" claim in the final paragraph unless the body has actually earned it.

### 6. Control tone strength

- Use academic restraint when evidence is partial.
- Prefer scoped claims such as "在……范围内" or "现有结果表明" over absolute claims.
- In papers, conclusions must match evidence density.
- In textbooks, explanation can be firmer than in papers, but still should not overclaim.

### 7. Keep terminology and notation stable

- Keep repeated terms consistent across the whole passage.
- Do not casually switch among synonyms for key concepts.
- Respect discipline-specific capitalization, abbreviations, formulas, and symbol conventions.

## Textbook Mode

When the source is a textbook chapter, teaching note, or instructional explanation:

- Prefer clarity over ornament.
- Definitions should be explicit, but not ceremonial.
- Explanations should move from concept to condition to example, not from slogans to abstraction.
- Remove motivational filler and false urgency.
- Preserve teaching scaffolding where it helps the learner.
- If the original uses numbered steps because the concept is procedural, keep the numbering.

Common textbook fixes:

- compress repetitive setup paragraphs
- replace big claims with concrete explanation
- unify terminology across examples
- shorten "teacher voice" that sounds like policy prose
- turn rhetorical summary into direct recap

## Paper Mode

When the source is a paper, thesis, literature review, or research report:

- Preserve the argumentative skeleton.
- Keep citation markers exactly as given.
- Keep necessary qualification, boundary conditions, and uncertainty.
- Remove promotional phrasing and over-wide significance claims.
- Make the discussion sound argued, not marketed.
- Avoid switching between colloquial and formal registers.

Common paper fixes:

- reduce repetitive transition markers
- rewrite abstract nouns into explicit research actions
- tighten literature review summaries
- keep contribution claims proportional to evidence
- replace ornamental conclusion lines with scope, limit, or implication

## Deep Review

Read [references/academic-patterns.md](references/academic-patterns.md) when:

- the user wants a deep rewrite rather than light polishing
- the user asks why the text "has AI flavor"
- the text is for thesis, journal, conference, textbook, lecture notes, or academic publishing
- the draft has visible translationese or template repetition

Read [references/discipline-guardrails.md](references/discipline-guardrails.md) when:

- the text contains formulas, citations, domain terms, or methodological claims
- the user is working on STEM, social science, education, medicine, or law related writing
- precision matters more than fluency

## Output

Default output order:

1. Give the rewritten text first.
2. If the user asks for explanation, list the 3 to 6 most obvious AI-like problems.
3. If the user asks to preserve more original wording, provide a lighter version and a heavier rewrite version.

## Usage Examples

Typical requests that should trigger this skill:

- "用 humanizer-zh 把这段教材写得更像中文母语作者写的。"
- "把这段论文讨论部分降一点 AIGC 痕迹，但不要改动引文和结论强度。"
- "解释这段文字为什么 AI 味很重，再给我一个重写版。"
- "给我一个轻改版和一个重写版，术语和公式别动。"

## Final Check

Before replying, confirm all of the following:

- The passage reads like native Chinese prose rather than translated prompt output.
- Facts, citations, formulas, and terminology remain intact.
- The opening and ending still answer the same question.
- Paragraphs have distinct functions instead of repeating the same template.
- Claims are no stronger than the evidence supports.
- Textbook prose still teaches clearly.
- Paper prose still sounds publishable and properly qualified.
