---
name: update-github-info
description: Refresh GitHub Info with practical updates from the GitHub Blog and Changelog.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
tools:
  edit: true
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    title-prefix: "[GitHub Info] "
    draft: false
    allowed-files:
      - "site/content/github-info.md"
---

# Update GitHub Info

Read `notes/mona-notes.md` and the current `site/content/github-info.md` before making changes.

Fetch both of these official sources:

- https://github.blog/latest/
- https://github.blog/changelog/

Find recent updates that are useful to developers and fit Mona's practical editorial angle. Verify details and dates from the source pages, avoid duplicating items already covered, and keep each summary short. Update only `site/content/github-info.md`; include a direct source link for every item derived from the GitHub Blog or Changelog. Preserve the existing editorial guidance and themes.

If there are no relevant, verifiable updates to add, leave the file unchanged and use `noop` with a brief explanation.

When the file changes, open a pull request using the configured safe output. Keep the PR description concise, summarize the updates with their source links, and ask Mona to review. Do not write directly to the default branch.
