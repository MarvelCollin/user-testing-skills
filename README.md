# User Testing Skills

Claude Code plugin that acts as a human user to test websites for usability, UX quality, accessibility, performance, and user flow issues.

## Skills

| Skill | Trigger | Purpose |
|-------|---------|---------|
| `/ux-tester` | Manual | Full UX audit — orchestrates all other skills |
| `/ux-flow-test` | Manual | Test a specific user flow end-to-end |
| `/ux-accessibility` | Manual/Auto | WCAG A/AA/AAA compliance audit |
| `/ux-compare` | Manual | Head-to-head comparison of two websites |
| `/ux-report` | Manual | Compile findings into prioritized report |

## Installation

```bash
claude plugin add ./
```

## Usage

```
/ux-tester https://example.com
/ux-tester https://example.com mobile
/ux-flow-test https://example.com "sign up and create first project"
/ux-accessibility https://example.com
/ux-accessibility https://example.com AAA
/ux-compare https://site-a.com https://site-b.com
/ux-report
/ux-report ./reports/my-report.md
```

## Project Structure

```
.claude-plugin/plugin.json    Plugin manifest
skills/                       Skill definitions
  ux-tester/                  Full audit orchestrator + shared resources
    SKILL.md                  Main skill
    browser-protocol.md       Browser interaction rules
    personas.md               6 test personas
    scoring-rubric.md         8-category weighted scoring
    ux-heuristics.md          Nielsen's 10 + cognitive load framework
    templates/                Report and flow test templates
  ux-flow-test/               Goal-based user flow simulation
  ux-accessibility/           WCAG compliance auditor
  ux-compare/                 Side-by-side website comparison
  ux-report/                  Report compiler with partial data handling
scripts/                      Automation scripts (bash + PowerShell)
evals/                        Skill evaluation test cases
```

## Scripts

| Script | Purpose |
|--------|---------|
| `lighthouse-audit.sh/.ps1` | Lighthouse performance + a11y scan |
| `axe-scan.sh/.ps1` | axe-core accessibility violations |
| `perf-check.sh/.ps1` | TTFB, compression, cache header checks |
