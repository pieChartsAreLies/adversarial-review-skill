# Adversarial Review Skill

A Claude Code skill that sends your designs and implementation plans to Gemini for comprehensive adversarial review before you proceed to implementation.

## What It Does

After you finalize a design document or implementation plan, this skill routes it to Gemini 3.1 Pro for a second opinion. Gemini acts as an experienced technology leader stress-testing every aspect:

- **Architecture** - structural soundness, scalability, maintainability
- **Product thinking** - does the solution actually solve the right problem?
- **Definition quality** - are requirements clear and complete?
- **Risks** - what could go wrong that hasn't been considered?
- **Missed opportunities** - features and capabilities the team hasn't thought of yet

Findings are grouped by severity (Critical, Important, Consider) with missed opportunities called out separately. You pick which items to incorporate before moving forward.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- A Gemini MCP server configured with `review_design` and `review_plan` tools

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

The skill integrates into your workflow automatically. When a design or plan is ready, it offers a Gemini review. You can accept or skip. If you accept, findings are presented for you to selectively incorporate before proceeding.

## License

MIT
