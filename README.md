# Adversarial Review Skill

A Claude Code skill that sends your designs and implementation plans to a multi-vendor model panel (via OpenRouter) for comprehensive adversarial review before you proceed to implementation.

## What It Does

After you finalize a design document or implementation plan, this skill routes it to three non-Anthropic models in parallel (GPT-6.1 Sol, Grok 4.7, GLM 5.3 Flash X). Each acts as an experienced technology leader stress-testing every aspect:

- **Architecture** - structural soundness, scalability, maintainability
- **Product thinking** - does the solution actually solve the right problem?
- **Definition quality** - are requirements clear and complete?
- **Risks** - what could go wrong that hasn't been considered?
- **Missed opportunities** - features and capabilities the team hasn't thought of yet

Claude merges the three reviews, deduplicates, and puts findings raised by more than one reviewer first. Findings are grouped by severity (Critical, Important, Consider) with missed opportunities called out separately. You pick which items to incorporate before moving forward.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- An MCP server named `adversarial-reviewer` exposing `review_design` and `review_plan` tools, plus an OpenRouter API key

## Installation

Add the skill to your Claude Code configuration:

```bash
claude skills add /path/to/adversarial-review-skill
```

Or clone this repo and reference it directly:

```bash
git clone https://github.com/pieChartsAreLies/adversarial-review-skill.git
claude skills add ./adversarial-review-skill
```

## When It Triggers

- After a design document is approved (e.g., output from a brainstorming workflow)
- After an implementation plan is written
- When you explicitly ask for a second opinion or adversarial review
- Before major implementation work begins

## Usage

The skill integrates into your workflow automatically. When a design or plan is ready, it offers a panel review. You can accept or skip. If you accept, findings are presented for you to selectively incorporate before proceeding.

## License

MIT
