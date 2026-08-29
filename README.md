# Commit Garden

A tiny GitHub Actions repository that periodically grows a visible activity log by making a random number of small commits.

## How it works

- Runs once per day on the default branch.
- Chooses a random commit count between `MIN_COMMITS` and `MAX_COMMITS`.
- Appends one timestamped entry to [`activity/growth.log`](activity/growth.log) per commit.
- Can also be started manually from the **Actions** tab.

## Setup

1. Create an empty GitHub repository and push this directory to it.
2. In the repository settings, enable **Actions** if needed.
3. Optional: add a repository secret named `COMMIT_EMAIL` containing an email address associated with your GitHub account. GitHub only attributes commits to your profile when the commit email is associated with that account.
4. Optional: add repository variables named `MIN_COMMITS`, `MAX_COMMITS`, and `COMMIT_NAME` to customize the defaults.

The default range is 1–3 commits per scheduled run. Manual runs can override the range through workflow inputs.

This repository is intentionally transparent: every generated commit changes only the activity log and uses a `chore: grow the garden` commit message.
