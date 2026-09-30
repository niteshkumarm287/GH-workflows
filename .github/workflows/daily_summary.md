---
name: Daily Repo Summary
on:
  schedule:
    - cron: '0 9 * * 1-5'
  workflow_dispatch:
engine: copilot
permissions:
  contents: read
  issues: read
  pull-requests: read
safe-outputs:
  github-token: ${{ secrets.COPILOT_GITHUB_TOKEN || secrets.GITHUB_TOKEN }}
  create-issue:
    title-prefix: "[Daily Sync] "
    labels: [status, automated]
---

# Your Task
Analyze all the pull requests and issues opened in this repository over the last 24 hours. 
Summarize the core engineering changes and open blockages. 
Create a new GitHub issue titled "Daily Engineering Sync: [Date]" containing this summary.
