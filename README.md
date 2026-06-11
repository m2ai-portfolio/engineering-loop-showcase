# Tear It Down and Rebuild It

A public showcase of what happens when you ask Claude Code to **"review, tear down, and rebuild"** a skill instead of "improve it." The phrase triggered Claude Code's skill-creator methodology, which ran a full engineering loop on a goal-decomposition skill (`decompose-goal`): callsite research, human design decisions up front, a frozen snapshot of the old version, a rewrite, four A/B evals in fresh subagents, assertion-based grading with written evidence, an aggregate benchmark, and a human review gate at the end.

## Headline numbers

| Metric | Old skill | Rebuilt skill |
|--------|-----------|---------------|
| Pass rate (mean across evals) | 74.2% ± 28.6% | **100% ± 0%** |
| Assertions passed | 17 / 23 | **23 / 23** |
| Wall-clock per run | 47.5s | 47.4s |
| Tokens per run | 76,645 | 77,553 (+1.2%) |

The killer detail: in the JSON-mode eval the old skill scored **2/6** vs the rebuild's **6/6**. The old skill promised JSON output in its description but never defined a schema, so the model invented an ad-hoc shape that breaks any programmatic consumer. Four of six failures traced to one missing paragraph.

## What's here

- `index.html` — a self-contained, zero-dependency showcase page: the loop, the benchmark, side-by-side eval evidence (all four evals, old vs new outputs with per-assertion grades), before/after skill excerpts, and five copy-paste prompt templates to run the same pattern yourself.

The site is published via GitHub Pages; open `index.html` in any browser to view it locally.

## Note on sanitization

All file paths, hostnames, and URLs in the prompts, outputs, and grading evidence are illustrative placeholders. Structure, scores, and grader verdicts are otherwise verbatim from the original eval workspace.

Built with Claude Code's skill-creator methodology.
