![banner](banner.png)

# advisory-watch

I built this as part of my GitHub Developer Program portfolio. It is a GitHub Actions workflow that watches the GitHub Advisory Database for the packages a project depends on. When a new advisory lands for something in your dependency list, it shows up in your own repository as a digest issue, where your team already works, instead of surfacing later as a production surprise.

Status: scaffold. The workflow interface is defined and the polling engine is the next build step.

## Workflow

- File: `.github/workflows/advisory-watch.yml`, workflow name `advisory-watch`
- Triggers: schedule, cron `17 6 * * 1` (Monday at 06:17 UTC, weekly), and manual `workflow_dispatch`
- Job: `watch` on `ubuntu-latest`, with a single step named `Scaffold status` that prints the scaffold status message
- This repository contains a workflow, not a custom action: there is no `action.yml`, so it cannot be referenced with a `uses:` step in another workflow

## What it will do

- Read the project's dependency list on a weekly schedule
- Poll the GitHub Advisory Database for new advisories that match those packages
- Open or update a single digest issue with what it found
- Stay quiet on the weeks when nothing new matches

Built by Gavin Blacklock (Epsilon0xCell).
