# Auto Commit Bot 🌳

Keep your GitHub activity graph green with automated commits powered by [GitHub Actions](https://github.com/features/actions).

[![Auto commit](https://github.com/uv3704/auto-commit-test/actions/workflows/autocommit.yml/badge.svg)](https://github.com/uv3704/auto-commit-test/actions/workflows/autocommit.yml)

![uv3704's GitHub Stats](https://ghchart.rshah.org/uv3704)

## How It Works

1. A GitHub Actions workflow runs on a scheduled cron job (or manually via `workflow_dispatch`).
2. It updates the `LAST_UPDATED` file with the latest UTC timestamp.
3. It commits the changes under your configured GitHub user email/name and pushes them back to `master`.
4. Your GitHub contribution graph turns green! 🟩

## Configuration

- **Schedule Frequency**: Edit the cron expression in [`.github/workflows/autocommit.yml`](.github/workflows/autocommit.yml#L8).
  - Every 6 hours (default): `"0 0,6,12,18 * * *"`
  - Every hour: `"0 * * * *"`
  - Daily at midnight UTC: `"0 0 * * *"`
- **Author Information**: Ensure `user.email` in `autocommit.yml` matches your primary GitHub account email so commits are counted towards your stats.
- **Workflow Permissions**: In GitHub repository settings: **Settings** -> **Actions** -> **General** -> **Workflow permissions** -> **Read and write permissions**.

