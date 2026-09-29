---
name: Daily Repo Summary
on:
  schedule:
    - cron: '0 9 * * 1-5' # Runs every weekday morning
engine: copilot
permissions:
  issues: read
  pull-requests: read
safe-outputs:
  create-issue:
    title-prefix: "[Daily Sync] "
    labels: [ automation ]
    max: 1
---

# Your Task
Analyze all the pull requests and issues opened in this repository over the last 24 hours. 
Summarize the core engineering changes and open blockages. 
Create a new GitHub issue titled "Daily Engineering Sync: [Date]" containing this summary.
