# SEWV Support Knowledge Base — 04: Tools, Glossary & Labeling

## Tools in use

- **Gmail** — shared support inbox. Each teammate has their own label/folder.
- **Teachable** — course platform/LMS. Accounts, purchases, subscriptions, enrollments, coupons, refunds (within 30 days).
- **Kit** (formerly ConvertKit) — email marketing. **Tags** mark what someone has purchased/joined/opted out of. **Sequences** are automated multi-email series triggered by a tag — removing a tag doesn't always remove someone from an in-progress sequence (sometimes needs manual removal from the automation itself, no bulk option). **Broadcasts** are one-off manual sends. **Automations** connect trigger tag → filters → tag changes → sequence enrollment → follow-up actions.
  - Claude has live, direct Kit API access — subscriber lookup by email, tag checks, engagement data, sequence/broadcast listing, tag application.
  - The Chrome extension showing subscriber tags in Gmail is not part of the workflow (doesn't work with delegated access; Ailsa doesn't use it).
- **Gmail draft tool cannot attach files**, despite an "attachments" field existing in the schema — not yet supported. Workaround: link directly to a reference image in Drive instead of a true attachment (student clicks to view). Card-update and Facebook-replay reference images are already handled this way — see the relevant entries below.
- **Stripe** — primary payment processor. Used for refunds on purchases older than 30 days (Teachable's own refund button disappears at that point). We no longer contest payment disputes (see the Stripe-dispute rule in file 01 #12) — disputes are deleted/ignored, not fought.
- **PayPal** — secondary processor, common with international students. Cannot be used for subscription payments (Monthly/Yearly Membership) — one-time-payment products only. Used for refunds on purchases 30+ days old paid via PayPal.
- **Zapier** — syncs Teachable ⇄ Kit (e.g. auto-canceling old Monthly payments on a Lifetime upgrade). Known to be imperfect — always double-check the Kit side manually after a Teachable change.
- **Monday.com** — "Important Links" tab holds the promotion schedule/calendar.
- **Promotions calendar spreadsheet** — master promo calendar (Google Sheets, tab per year). Live reference to check, not something to copy into this knowledge base: https://docs.google.com/spreadsheets/d/11bsBRUw6_3u6CydUq9Fg9EnLRaQXZz04Pxz-wdkoE0I/edit
- **Canva** — completion certificates.
- **hi@yourteacher.ai (Peter)** — external paid support for Vanessa AI app issues; route bugs here, don't troubleshoot internally.
- **Course sign-in page**: https://speak-english-with-vanessa.teachable.com/sign_in

## Glossary / naming conventions

- **FFC** = Fearless Fluency Club. **FFC 3.0** = current Monthly Membership structure. **MM** = Monthly Membership.
- **LC1–LC5** = the five 30 Day Listening Challenge packs — internal shorthand only; use the theme name when talking to a student (e.g. "the 30 Day Listening Challenge: Passion").
- **PV** = Phrasal Verb challenge; **VC** = Vocabulary challenge (both part of the 90 Day Challenge).
- **WBC** = Word-Boosting Challenge (60-day).
- **SC / SC1 / SC2** = Speaking Challenge. Plain "SC" internally usually means the original (SC1, 2022/23). SC2 is current (July 2026, Vanessa-AI-integrated) — customer-facing name "30 Day Speaking Routine."
- **"Free Opt-in"** — Kit tag applied the first time someone downloads any free lead magnet; triggers the welcome sequence. Only applied once ever.
- **"Finished Freebie"** — applied when someone completes the welcome automation (not just downloads something). Until then, they receive only welcome-sequence emails, no broadcasts.
- **"No Promos: In FFC 3.0 Automation"** — temporary tag suppressing all other marketing during new-FFC-student onboarding.
- **Modules** (current term; "lesson set" is outdated) — ~40 topic-based FFC modules, several lessons each (hence "248 lessons" in marketing). All available to every Monthly/Yearly/Lifetime student automatically; new modules added 3×/year, no action needed from students.
- **2026 Study Plan**: https://drive.google.com/file/d/1RQmK_z48Y83lfJxSoP_GxJgfqzi5nmmh/view?usp=sharing — names the current featured module with its direct link. Safe to send straight to a student.

## Gmail label taxonomy — the daily workflow

**Claude/\* labels** (final structure):

- **Claude/Need sent** — customer-facing reply drafted, ready to send as-is.
- **Claude/Need admin (high priority)** — needs backend work (Kit/Teachable/Stripe/PayPal) before anything can be sent or is resolved.
- **Claude/Need deleted** — delete candidate, flagged for a human to confirm rather than deleted outright.
- **Claude/Possible unsubscribe** — explicit "stop emailing me" signals.
- **Claude/Possible spam** — ambiguous spam calls.

## Labeling rule — corrected (no thread left unlabeled)

Every thread touched during a check-email pass must end with a label applied and INBOX removed (or UNREAD-only removal for teammate handoffs, per the rule below). Nothing is left sitting bare in the inbox for "later judgment" — that includes ambiguous cases.

- No backend action needed (pure reply) → **Claude/Need sent** only.
- Backend action needed (refund, tag change, Teachable lookup, coupon creation, etc.) → **Claude/Need admin (high priority)** only — do not also add Need sent. The admin checklist draft already contains the fully-written customer reply as part of the two-draft pattern below; a separate Need sent label would just duplicate the task across two folders.
- Delete/spam/unsubscribe candidates (no draft needed) → apply the matching label directly, no draft required.
- **Genuinely ambiguous but clearly important** — doesn't fit a delete/admin/sent bucket, and a human should personally decide how (or whether) to respond (e.g. a personal note from a longtime partner, an unusual one-off request) → label **VANESSA** (the existing per-person folder) and remove INBOX. This routes it to Vanessa's own queue instead of leaving it in the shared inbox. Use this sparingly: it's for threads that are clearly worth a human's attention, not a catch-all for uncertainty. When genuinely unsure whether something is delete-worthy noise vs. important, the recalibration default in 01-email-response-playbook.md (default to Claude/Need deleted when unsure) still applies — VANESSA is for the smaller set of cases where it's clearly not noise, just not triageable by rule.

**Remove INBOX the moment a draft is created**, in the same pass — keeps the general inbox showing only unprocessed items. This applies whenever any draft (customer reply, admin checklist, or both) is created on a thread.

**Teammate handoff labels (Amber, etc.) keep UNREAD — only Claude/\* and VANESSA labels used this way clear it.** When routing to another teammate's folder (e.g. Amber, for pronunciation feedback Claude can't evaluate), remove INBOX but *not* UNREAD — teammates rely on their own unread flag to know something's waiting. This is different from Claude/\* and VANESSA labels, where clearing UNREAD is correct since it represents the thread being resolved, drafted, or deliberately routed to a human — not a pending handoff.

**Two-draft workflow for anything needing backend admin work:**

1. **The admin checklist first** — to: contact@speakenglishwithvanessa.com as a safe placeholder (the Gmail draft tool rejects a fully empty "to" field), subject "🔧 ADMIN TASKS — DO NOT SEND," body containing the fully-written-out steps (not a pointer to a procedure number) with that student's actual details filled in.
2. **The customer-facing draft second (last)** — Gmail surfaces whichever draft was created most recently as the primary/visible one in the thread view, so creating it last makes it the one that displays first when the thread is opened. This matters since Vanessa wants the student-facing draft visible by default, with the admin checklist as the secondary follow-up action.

**Scope: only threads with activity in the last 30 days.** See file 00 for the full rule — applies to every source and destination.

## Full existing label structure (reference)

- **Per-person folders**: AILSA, NORAH, VANESSA, Amber — each with High/Low Priority and Reference/Informational sub-labels.
- **Admin Archive** (and nested sub-labels) — reference/record-keeping, not regularly checked:
  - **Certificate** — applied after sending a challenge-completion certificate (any challenge except Speaking Challenge).
  - **Opportunities** — collab/brand pitches that are language-related and genuinely interesting, or feature announcements worth a later look (most collab pitches are deleted outright per playbook #18 — this is for the minority worth flagging).
  - **Payment** (+ Canceled Subscription, Failed Billing Attempt, Disputes, SC Refund Sent) — fully automatic Gmail filters, no manual action needed.
  - **Taxes** — fully automatic filter for the tax/payroll accountants; goes straight to Vanessa.
  - **Testimonial** — applied when a message contains usable marketing-testimonial language.
  - **Vanessa AI** — largely obsolete; Vanessa-AI support questions now route straight to Peter (hi@yourteacher.ai) instead.
  - **Zoom Summary** — fully automatic filter for auto-generated Zoom call summaries.
- **SEWV Newsletter** — catches replies to Kit-sent broadcasts/newsletters (not a perfectly reliable filter; some still land in the general inbox). Not necessarily different from the general inbox in terms of how Claude should treat it.
- **VANESSA/Vanessa Informational** — Vanessa's own misc. reference bucket.
- **VANESSA/Vanessa: Archive/Vanessa: TEAM** — intentionally unused going forward (Vanessa emails the plain VANESSA label directly instead); if anything lands here, also apply plain VANESSA so it doesn't get missed.

## Verifying FFC membership before assuming it

Don't assume someone is an active FFC member just because their message implies it (mentioning "the audios," "the exercises," wanting to talk to "other members"), **except** for replies to the Day 4/Day 6 "7-Day FF" sequence — receiving that sequence at all already confirms active membership, so no separate check is needed there (see file 01 #27).

For every other membership-assuming context (sharing the Facebook group secret code, finalizing any other membership-assuming reply): check Kit first (`Kit:list_subscribers` by email, `include: ["tags"]`) for a membership tag (e.g. "FFC 3.0" / "FFC Purchased," or the Monthly Membership tag "FFC: MM"). If found, proceed normally. If not found, route to Claude/Need admin with a checklist to confirm actual status in Teachable — Kit tags can be out of sync with real purchases — and word the customer draft conditionally rather than assuming either way, or use the **two-option draft format**: a single draft containing both versions clearly labeled ("===== IF [SHE/HE] IS an FFC member =====" / "===== IF NOT =====") with a short admin note at the top explaining why it landed in Need admin, rather than two separate drafts.

## Draft creation & threading — mechanics

**Every reply opens with "Hi [Name],"** — see file 00 for the name-finding priority order. This applies even to template-based replies that show the body starting mid-sentence.

**Links** as hyperlinked text via `htmlBody` with a real `<a href>` tag, not raw URLs — except the Teachable sign-in link, which stays plain/visible. The visible anchor text must be words, never the raw URL itself. See file 00 for the footer format and the full pre-send checklist.

**Facebook group live-lesson replay** — whenever a reply directs a student to a recorded replay (timezone conflicts, Day 6 mentions, "how do I catch up" questions), include the screenshot image showing exactly where to click, hyperlinked as "Here's a picture": https://drive.google.com/file/d/1MEpVO6PS1cXi0hfF2H8tgxAUPBOpbmJk/view?usp=sharing Pair it with: look for **"Media" or "Videos"** at the top of the Facebook group (wording/steps vary by device — don't phrase it as two sequential steps).

**Card-update image link** — when a reply tells a student how to update their card on file (failed automatic payment, or they mention a new card), include this image hyperlinked as "Here's an image": https://drive.google.com/file/d/1jVcOp8XDEa2il_BbcVYt6sZkfBX1HsYp/view?usp=sharing Pair it with the plain Teachable sign-in link.

**Match the reply to the exact ask** — re-read the specific wording of what's being requested (cancel only vs. refund vs. both) before picking a template, rather than pattern-matching on subject line or general vibe. When genuinely ambiguous, ask Vanessa/Ailsa rather than guess.

**"I cannot take $X every month... I did not opt for it"** = an implicit cancellation request, not just a clarification ask — go ahead and cancel (Procedure A) and mention it's been canceled in the reply, in addition to explaining the pricing mechanics. Contrast with a purely neutral question ("just confirming it's $35/month, right?"), which doesn't need this treatment.

**Billing discrepancy (charged more than expected)** — check Teachable for an accidental order bump alongside the main product before assuming a currency-conversion explanation. Requires an actual lookup, so routes to Claude/Need admin.

**"Please get my written approval before charging me again"** — explain the membership renews automatically each month with no manual approval step; if comfortable continuing, no action needed; if not, they're welcome to cancel anytime.

**Distinguishing a new lead's "I have no money" from an existing customer's cancel/refund request** — misspellings are not a reliable signal. Better signals, in order: (1) what they're replying to (a marketing broadcast → likely a prospect declining; a transactional email like a receipt or payment-notice → likely an existing account), (2) explicit account language ("my subscription," an order ID) vs. aspirational language ("I wish I could join"), (3) the verb used ("cancel/refund/stop charging" vs. "I want to join but can't afford it"), (4) when still unclear, check Kit for an active membership tag. Default to Claude/Need deleted when none of these clearly point to an existing account.

**"Which lesson should I start with" near month-end** — if fewer than 5 days remain in the current month, recommend starting with next month's module instead of the current one; otherwise point to the 2026 Study Plan as usual.

**Recognizing the Yearly-upgrade automated email from a reply alone** — FFC Monthly students automatically receive an upsell email in their first month offering the Yearly plan at $19/mo (the word "Upgrade" in the subject/CTA, e.g. "Upgrade to the Yearly Membership," is the tell). If a reply is quoting/responding to that email, the recipient is already an existing paying Monthly member, not a new lead — a reply like "I already paid $X" is about their existing membership, not confusion about whether to buy. Acknowledge their existing membership first, then address whatever confusion they raised.

**Self-sent newsletter copies** (sender = recipient = contact@speakenglishwithvanessa.com, no third-party involved) — always apply the full Claude/Need deleted label, don't just clear the unread status without labeling.

**Recognizing a reply to the newsletter Welcome Sequence** — Kit's "Welcome Sequence" (id 1936304, ~21,000 subscribers) is the nurture sequence every new newsletter subscriber gets, roughly one email/day. If a reply's quoted original matches one of the 24 subject lines below, the sender is a newsletter subscriber, not a paying student — read any course/PDF/payment question through that lens.

1. I cried ;(
2. An unexpected surprise!
3. My *simple* system for FLUENT English
4. Don't waste your money on THIS!
5. Does the course really work? You might be surprised!
6. Save 97% and speak FLUENT English
7. Don't Miss the $1 Offer🚨
8. Meet Vanessa
9. What's inside?
10. What should I do?
11. The Fearless Fluency Club is closing down soon ⏳ (12 hrs after #10)
12. [Final Warning] Gone at midnight… 🕛 (6 hrs after #11)
13. Did you miss the BIG SALE on my premium course?
14. 5-Minute English: In a heartbeat
15. 5-Minute English: A household name
16. 5-Minute English: Come by!
17. 5-Minute English: Go out!
18. 5-Minute English: Quiz time!
19. Want more?
20. A little quiz
21. It's amazing 🤩
22. We start soon
23. Last call
24. Did you miss the chance to join for $1?

The actual free-PDF-delivery email (below) isn't part of this sequence — sent separately, immediately on signup — so every subscriber already has their PDF before email #1 goes out. A reply to any of the 24 above asking for "the PDF" always means re-sending the original lead-magnet, never a course-content question.

**Free PDF Worksheet delivery email.** Subject: **"Your FREE PDF worksheet is here"**

> Congratulations on choosing to improve your English skills! Click the link below to download your free PDF worksheet. [Download free worksheet here] Keep up the great work with English! Your teacher, Vanessa

A reply to *this specific email* reporting a problem is a download/access issue, not a request for a different PDF. Since Vanessa has offered multiple different free worksheets over time and this email doesn't name which one, ask which worksheet they're looking for before troubleshooting or re-sending — updated general template for "where's my PDF" (not this specific email, the broader question): "Your free PDF worksheet should be inside the confirmation email you received after signing up, just click the download button there. Please check your SPAM and PROMOTIONS folders, too. If you can't find it, let me know and I'll help you track it down."

**"Code" in FFC context** usually means the Facebook group secret code ("English is fun"), not a discount code — don't assume "code" means a coupon unless context is clearly about checkout/pricing.

**Recognizing "lesson guide" requests by module theme name** — when a student names a themed module (e.g. "the adoption lesson") and asks for a PDF/guide, they're asking for that module's lesson guide, found in the Facebook group's "FILES" section — not the general Worksheet Library or a "check your confirmation email" response.

**"I stopped receiving [course emails]"** — don't default to "check your spam folder." Route to Claude/Need admin and check Kit for (1) active membership, (2) still subscribed to that specific sequence — likely cause is an accidental unsubscribe-from-this-sequence click, not a technical failure.

**"Re: A quick question" — check content, not just subject.** Multiple different Kit broadcasts share similar subject lines. One variant to watch for: "What topic would you love to study in The Fearless Fluency Club?" — if the student lists 4+ topics, flag for Vanessa to review (don't delete); otherwise (1–3 topics or vague answers) route to Claude/Need deleted as usual.

**Asking for the price in Rupees** signals "can't pay" — route to Claude/Need deleted rather than replying with a detailed pricing breakdown.

**Discontinued program: Pronunciation Intensive / Speaking Intensive** (small-group format, ran May–June 2026). If a student mentions missing "direct communication in a small group" or similar, this is very likely what they're referencing — name it directly as discontinued and redirect to the current Sunday live lesson + Fearless Fluency Chats.

## Open items / gaps

1. **Procedure B (Kit non-member cleanup) — Zapier automation test.** Check back periodically to confirm it's working reliably; manual steps kept in file 02 as fallback.
2. **Vanessa AI SAVE70 coupon** — seasonal (September), don't mention outside its active window; verify dates each time it reopens.
3. **New standalone Vanessa AI promotion** — planned, not yet run; add to file 03 once a FAQ sheet exists.
4. **Teachable connection for enrollment verification** — blocked on Windows support as of last check; all Teachable-dependent checks stay manual until resolved (Zoom Room enrollment gating, current enrollment, cancellation/refund status).
5. **Reference-screenshots Drive folder** — the card-update and FB-replay images are already linked directly (see above); other file 06 templates that still say "I'll attach a photo" should be updated to direct image links as they come up for review, since the draft tool can't attach files.
6. **`update_draft` threading bug is the norm, not the exception** — see file 07. As of early August 2026, every use of `update_draft` on an existing draft observed in practice has detached it onto an orphaned thread. Continue using the create_draft + replyToMessageId + DISREGARD-the-old-one workaround by default; worth flagging to whoever manages the Gmail connector as a live bug rather than a rare edge case.
