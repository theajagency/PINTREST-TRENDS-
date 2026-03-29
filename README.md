# Pinterest Fashion Trend Tracking System

## What This Is
A self-contained knowledge system for monitoring daily Pinterest fashion trends. Every file here exists so that a scheduled agent (or a person) can run accurate searches and produce consistent reports with zero prior context.

## Files

| File | What It Does |
|---|---|
| `keywords.md` | Every search term, organized by category |
| `rules.md` | What to avoid, guardrails, prom note |
| `signals.md` | How to call a keyword UP / STABLE / WEAK |
| `report-template.md` | Copy-paste format for each daily report |
| `agent-prompt.md` | Full self-contained prompt for the scheduled CCR agent |
| `reports/` | Folder where daily reports are saved as `YYYY-MM-DD.md` |

## How It Works
1. Every day at 10:30 AM Eastern, a scheduled Claude agent runs using the prompt in `agent-prompt.md`
2. The agent searches Pinterest for every keyword in `keywords.md`
3. It scores each keyword as UP / STABLE / WEAK using the criteria in `signals.md`
4. It follows the rules in `rules.md` (avoids, guardrails)
5. It outputs a report in the format defined in `report-template.md`
6. The report is saved to `reports/YYYY-MM-DD.md`

## View Scheduled Agent
https://claude.ai/code/scheduled

## Update Keywords or Rules
Edit `keywords.md` or `rules.md` directly, then update `agent-prompt.md` to match (the agent prompt must be self-contained).
