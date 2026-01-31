# p2 Demo

This repository demonstrates the [p2 GitHub Project Scheduler](https://github.com/octoberswimmer/p2-github-scheduler).

## Setup

1. Install the [p2 GitHub App](https://github.com/apps/october-swimmer-p2)
2. Create a GitHub Project with the required fields (see below)
3. Add issues with estimates and watch the scheduler calculate completion dates

## Required Project Fields

| Field Name | Type | Description |
|------------|------|-------------|
| Low Estimate | Number | Low estimate in hours |
| High Estimate | Number | High estimate in hours |
| Scheduling Status | Single select | Set to "On Hold" to exclude from scheduling |
| Expected Start | Date | Calculated start date (written by scheduler) |
| Expected Completion | Date | Mean completion date (written by scheduler) |
| 98% Completion | Date | 98th percentile completion date (written by scheduler) |

## How It Works

When issues are updated (or daily at 6am UTC), the p2 scheduler:

1. Fetches all issues from the project
2. Respects task dependencies via GitHub's blocking relationships
3. Calculates completion date ranges based on estimates
4. Updates the date fields in the project

See the [documentation](https://octoberswimmer.com/tools/p2/) for more details.
