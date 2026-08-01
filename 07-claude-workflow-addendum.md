# SEWV Support Knowledge Base — 07: Claude Workflow Addendum (Tool Mechanics)

Source: established through direct sessions with Claude (Anthropic), July 27–30, 2026\. This file is now scoped to Gmail/Kit tool behavior and mechanics only — content/policy corrections that used to live here (and in the now-retired file 08\) have been folded directly into files 00–06. Defer to those files for actual reply content, pricing, and policy.

## What "check email" means

When told to "check email" (or similar), without asking for permission first:

1. Pull new activity only — new threads and new replies since the last check. Don't re-surface pre-existing backlog; that's handled separately, on request.  
2. Check both `in:inbox` and `label:"SEWV Newsletter"` — the newsletter label lives outside the inbox view and won't show up in a plain `in:inbox` search.  
   - This label mixes old and new mail together — filter by date, not unread status. The label's unread count doesn't reliably distinguish new activity from old backlog nobody's gotten to yet.  
3. Triage per the priority system in file 00 and the scenario guidance in files 01/05/06.  
4. Draft replies automatically for anything needing one (high/medium priority) — don't ask permission first, just draft. Leave clearly delete-worthy items undrafted.  
5. Apply the real production labels (file 04\) so the inbox actually empties.

## Gmail search quirks

- `search_threads` with `query: label:Label_ID` can return zero results for some labels even though tool docs say to use label IDs, not display names. If a label search returns empty unexpectedly, retry with the quoted display name form (`label:"SEWV Newsletter"`) as a fallback.  
- Trust `Gmail:list_labels` for volume counts, not `search_threads`'s `resultCountEstimate` — the latter is a rough Gmail estimate that can be significantly wrong. Cross-check against `list_labels` before reporting any volume figure.

## Bug: `get_thread` fails once a thread is fully trashed

Vanessa's workflow trashes a thread right after replying. Once every message in a thread is trashed, `get_thread` fails outright with a permission error and cannot retrieve that thread's history at all. `search_threads` with `includeTrash: true` retrieves the same thread fine, trashed messages included. Once a student replies again, the new (non-trashed) message brings the thread back into view and `get_thread` works again — the failure window is specifically while the whole thread sits in trash with no live message on it.

**Fix:** don't rely on `get_thread` alone for any thread with more than one message. Prefer `search_threads` with `includeTrash: true` to reliably retrieve full context regardless of trash state. If `get_thread` fails, that's the signal to fall back to the trash-inclusive search rather than proceeding with partial context. This requires no change to Vanessa's own workflow — she can keep trashing after every send exactly as before.

## Bug: `update_draft` can silently detach a draft onto a phantom thread

Even without any trashed messages involved, calling `update_draft` on an existing draft can change its `threadId` to an unrelated, orphaned thread — disconnected from the real conversation, and easy to miss since the call still succeeds and returns normally. This has happened repeatedly and affected essentially every draft touched with `update_draft` in a session, including drafts that were correctly threaded beforehand.

**Fix:** don't trust `update_draft` for anything where correct threading matters. After using it, re-check the draft's `threadId` via `list_drafts` against the real conversation thread. If it doesn't match, don't keep patching with more `update_draft` calls — recreate the draft from scratch with `create_draft` and an explicit `replyToMessageId` pointing at the student's actual latest message (this method has been reliable when followed by a verification check), then mark the orphaned draft DISREGARD (see the disregard convention below). Prefer `create_draft` \+ `replyToMessageId` over `update_draft` by default whenever precise threading matters, rather than reaching for `update_draft` first and hoping it holds.

## Draft-creation conventions

- Always set `to` explicitly to the actual customer email address, rather than relying on `replyToMessageId` alone — contact-form notification emails route strangely (sender/recipient both show as [contact@speakenglishwithvanessa.com](mailto:contact@speakenglishwithvanessa.com)).  
- Two-draft pattern for backend-work threads: see file 04 for the labeling rule and creation order (admin checklist first, customer draft second/last, so it displays as primary).  
- The admin-checklist draft's "to" field can't be fully empty (the tool rejects it) — use [contact@speakenglishwithvanessa.com](mailto:contact@speakenglishwithvanessa.com) as a safe placeholder so an accidental send loops back into the inbox rather than reaching the student.  
- **DISREGARD convention**: when a draft needs to be abandoned (orphaned by a threading bug, superseded by a corrected version, created in error), don't just leave it — edit its subject to start with "DISREGARD — \[reason\]" and the body to explain what to use instead, so it's not confused with the correct one or accidentally sent.

## Drafts threaded off a trashed message may not surface properly

A common pattern, not a rare edge case: Vanessa's workflow means a thread can very frequently have its earlier messages sitting in Trash, with a newer student reply arriving later on the same thread. Before drafting on any thread with more than one message, check whether the specific message being replied to (via `replyToMessageId`) carries a TRASH label — if so, use the most recent non-trashed message in the thread instead. Threading a new draft off a trashed message risks the draft becoming hard to find in the normal Gmail UI, or in the worse cases described above, detached from the thread entirely.

## Reference: Teachable/Stripe subscription cancel \+ reactivate mechanics

Useful context for confusing "I canceled but got charged again" cases — this specific reactivation scenario is unusual, not a go-to explanation to reach for by default:

- If a student reactivates before their current billing cycle ends: the subscription continues normally, no immediate charge, billed as usual at the end of that cycle.  
- If the billing cycle ends before they reactivate: fully canceled, needs a new payment to re-enroll.  
- Mechanics: canceling sends a confirmation and the subscription stays active through the rest of the billing period with no further charges scheduled. Reactivating from the Stripe Customer Portal before the period ends simply continues the subscription as active — this can produce a charge that looks like "I canceled but got billed anyway" without anything having gone wrong on SEWV's end.

## Open item

The SEWV Newsletter label may contain older backlog mixed in among new activity (see "What 'check email' means" above) — per the 30-day scope rule in file 00, only new activity within that window gets triaged; older items in this label are addressed separately, on request.  
