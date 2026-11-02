# advisory-watch

I built this as part of my GitHub Developer Program portfolio. It is a GitHub Action that watches the GitHub Advisory Database for the packages a project depends on. When a new advisory lands for something in your dependency list, it shows up in your own repository as a digest issue, where your team already works, instead of surfacing later as a production surprise.

Status: scaffold. The workflow interface is defined and the polling engine is the next build step.

## What it will do

- Read the project's dependency list on a weekly schedule
- Poll the GitHub Advisory Database for new advisories that match those packages
- Open or update a single digest issue with what it found
- Stay quiet on the weeks when nothing new matches

Built by Gavin Blacklock (Epsilon0xCell).
