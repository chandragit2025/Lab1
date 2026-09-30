---
name: update-github-info
description: Keep the GitHub Info site current with practical updates from the GitHub Blog and Changelog.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
  pull-requests: read
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    draft: true
---

# Update GitHub Info

Read `notes/mona-notes.md` and the current `site/content/github-info.md` before making changes.

Use `web-fetch` to read both of these sources:

- https://github.blog/latest/
- https://github.blog/changelog/

Choose recent items that fit Mona's practical focus on helping developers learn GitHub faster. Update `site/content/github-info.md` with concise, useful summaries, keeping its existing editorial direction and structure where appropriate. Link each update to its original GitHub Blog or Changelog source, and do not present an item as new unless its publication date supports that.

Keep the change limited to `site/content/github-info.md`. Open one draft pull request with a clear summary of the selected updates for Mona to review. Do not write changes directly to `main` or make any other direct repository writes.