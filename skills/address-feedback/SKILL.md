---
name: address-feedback
description: Responds to pull request review feedback before the next push. Covers security bot findings, Cursor Bugbot comments, and a person's requested changes and comments. Use when a reviewer or bot leaves feedback on a PR and you are about to address it, or when the user invokes /address-feedback.
---

# Address feedback

Before you fix review feedback, ask whether the comment points at a single bug or at a flaw in the design.

Treat it as a design flaw if any of these is true:

- The same kind of finding comes back after you fix it.
- Your fix would add a new special case, workaround, or exception.
- Two or more comments trace back to the same root cause.

If it is a design flaw, stop patching. Explain the flaw and propose a design change on the PR, then make that change. A long string of small fixes is a warning sign, not progress.

A single bug is a local mistake. Fix that one thing.

This covers every kind of review feedback: security bot findings, Cursor Bugbot comments, and a person's requested changes and comments.

## Triage

Read all open comments together first. Group them by root cause. Decide fix versus redesign per group.

- [ ] Read all open comments together.
- [ ] Group them by root cause.
- [ ] Decide fix or redesign for each group.

## Before you push

Review your own diff the way the reviewer would. Look for the next comment they would leave.

If you changed CI or a workflow, list each job's secrets and the third-party code it runs. Third-party code means an action, script, or checkout you do not own. Make sure no job has both. A job that can read a secret and run someone else's code can leak that secret.

## Reply

Reply in each thread. Say what changed, or why the finding does not apply. Never resolve a thread without a reply.

## Related

- `/pr` — review and merge
- `/fix` — root cause over a symptom patch
