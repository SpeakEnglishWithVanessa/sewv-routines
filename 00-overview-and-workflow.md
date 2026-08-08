# SEWV Support Knowledge Base — 00: Overview & Workflow

Source: Ailsa's VA training tutorials, compiled July 2026; corrected and expanded through direct sessions with Claude, July 27–August 1, 2026\.

## Preferred reference-file format: Markdown

Upload the .md version of each numbered knowledge base file (00–07) when available, in addition to or instead of the .docx version. Reading a plain .md file is a direct read with no extraction step; reading a .docx requires unzipping and parsing the internal XML (or a LibreOffice conversion), which costs extra time and tool calls. If both a .docx and .md version of the same file exist, the .md version should be treated as the source of truth and read first.

## The business

Speak English With Vanessa (SEWV) sells English-fluency courses (the "Fearless Fluency Club" and related challenges) via Teachable, with email marketing/automation on Kit, and payments through Stripe (primary) and PayPal (secondary).

## Team & roles

- **Vanessa** — owner/instructor. Final say on judgment calls, non-standard discounts, and anything unusual (6–12+ month old refund requests, ambiguous collab offers, etc.)  
- **Ailsa** — senior VA / trainer. Day-to-day inbox lead; will be rewriting drafts herself once the inbox is handed over, without a review layer in between — so drafts need to be correct the first time, not just correctable.  
- **Amber** — English-content teacher. Handles grammar/pronunciation-specific student questions.  
- **Norah** — VA; works weekends and fills in when Ailsa is away.

Team members communicate by emailing/tagging each other directly, or by creating a draft and tagging the intended reader via the Gmail label system. Always start "Hi \[Name\]" and sign your own name.

## Scope: only act on activity from the last 30 days

The daily "check email" workflow only applies to threads with activity within the past 30 days. The inbox has years of old, already-resolved, or personal/internal threads that were never cleared out (old collab threads, invoices, hiring correspondence, etc.) — these are out of scope entirely. Don't label, draft, or otherwise touch anything older than 30 days. This applies to every source (general inbox, SEWV Newsletter label, etc.) and every destination. If old backlog needs cleaning up, that's a separate, explicitly-requested project.

## The general/main inbox and spam folder

The **general inbox** (no label applied) is mostly people who typed Vanessa's email address directly, or replied via the website contact form — not meant to be a strictly filtered view. **Spam folder**: checked occasionally, not routinely; empty it monthly after checking. Other Gmail system tabs (Updates, Promotions, etc.) already have their own filters — no need to check separately.

## Inbox goals

Empty the inbox every day; respond within 24 hours. This is a hard requirement, not a target: at the end of any "check email" pass, zero threads should remain sitting in the inbox unlabeled. Every thread gets a label of some kind — there is no "leave it for later, untouched" outcome. See 04-tools-glossary-and-open-items.md's labeling rule for exactly how ambiguous-but-important threads should be routed (the **VANESSA** label) instead of left bare.

- Lower-priority emails can wait a couple of days, but they still get labeled today, not left sitting unlabeled.  
- Delete an email after responding, unless keeping it for reference.  
- Busiest periods: last week/first days of each month, and any promo or challenge launch.

## Priority system

**High priority** (1–2 days): current students/paying customers; people likely to become customers (real interest, real questions); payment issues, signup errors, broken links; anyone tagged to you by a teammate.

**Low priority** (2–3+ days fine): people unlikely to ever become customers just asking general questions; threads needing a reply but not urgent.

**Safe to delete without a reply — the majority of the inbox.** See 01-email-response-playbook.md entry \#21 and the recalibration rule there for the full, current criteria — this list has been significantly tightened since the original version of this file, so defer to file 01 rather than an older mental model of what counts as "worth a reply."

## Standard email format

**Links**: insert as hyperlinked text ("click here to join," "here's the link"), not a raw pasted URL, in every draft — via `htmlBody` with a real `<a href>` tag. Gmail wraps every outgoing link in its own click-tracking redirect regardless of formatting; that's normal, not something wrong with the draft — the fix is only about what text is visible to the reader. **The visible text must be words, never the URL itself** — wrapping a raw URL in an `<a href>` tag is technically clickable but is still the wrong format; it must display as words like "here" or "click here to join."

**Exception**: the Teachable sign-in link ([https://speak-english-with-vanessa.teachable.com/sign\_in](https://speak-english-with-vanessa.teachable.com/sign_in)) stays as a plain, visible URL, not hyperlinked text, so students can easily copy/bookmark it for future logins.

Standard structure:

> Hi \[Name\],  
>   
> Thanks for your email. I'm so glad that you are learning English with me\!  
>   
> \[Answer / body content\]  
>   
> I hope that helps. Keep up the good work with English\!  
>   
> Vanessa English Teacher [www.SpeakEnglishWithVanessa.com](http://www.SpeakEnglishWithVanessa.com)

Footer link: text reads exactly [**www.SpeakEnglishWithVanessa.com**](http://www.SpeakEnglishWithVanessa.com), hyperlinked to [https://www.SpeakEnglishWithVanessa.com](https://www.SpeakEnglishWithVanessa.com) (plain text body: no raw `https://` in front, to avoid Gmail's own tracking-wrapper). **The sign-off name "Vanessa" is never itself a hyperlink** — only the website line beneath it is a link. If "Vanessa" appears underlined/linked to anything, that's a formatting error to fix before sending.

## Reply language

**All replies are written in English, regardless of what language the student wrote in.** This applies even when the student writes in Spanish, French, or any other language — read/understand their message in its original language to figure out what they're asking, but always draft the reply in English. Do not translate the reply into the student's language, and do not mix languages within a reply.

Other notes:

- If mid-thread with someone (several emails already exchanged), a shorter "Thanks for your email" is fine instead of the full opener.  
- Prefer plain, simple wording ("can" instead of "are able to") — most recipients are English learners. Avoid idioms/advanced phrases (e.g. "ease up") — don't try to rephrase them, just cut the sentence rather than keep an idiom in a different form.  
- Capitalize course names as proper nouns: "the Fearless Fluency Club," "the Monthly Membership."  
- No em dashes in student-facing content — use a comma or colon instead. Internal notes/checklists can still use dashes.  
- One sentence per line reads better for ESL readers in promotional/marketing copy; standard support replies stay in normal paragraph form.

## Zoom-call link — always use the current standard link

Anytime a reply mentions the Sunday Zoom call, Fearless Fluency Chats, or "practicing with the community" — in a Day 4 reply, a Day 6 reply, or any other scenario — hyperlink that mention to the standard Zoom link: [**https://www.facebook.com/events/756102087353777/756102227353763/**](https://www.facebook.com/events/756102087353777/756102227353763/). This applies unconditionally whenever those words appear in a draft, not just when it feels relevant to the student's stated goal — this is the single most common miss in Day 4/Day 6 drafts, so treat it as a hard rule rather than a judgment call. Enrollment gating still applies: only share this with currently enrolled FFC students (see file 05). Keep the Meeting ID (871 7101 8794\) and Passcode (speak) as plain-text backup where a template already includes them.

## Pre-send checklist — required before finalizing every draft

Run through all of the following as a distinct final pass, not just something to keep in mind while writing:

1. **Comma-splice check.** Comma splices (two independent clauses joined only by a comma, no conjunction) are the most common recurring grammar error. Re-read every sentence and test each comma: cover up everything before it and everything after it — if both halves could stand alone as a full sentence, it's a splice. Fix with a period \+ capital letter, a coordinating conjunction (and/but/so/or), or a semicolon if the clauses are closely related.  
2. **Zoom-link check.** If the draft mentions the Sunday live lesson, Fearless Fluency Chats, or the community Zoom call in any form, confirm it's hyperlinked to the standard link above (not an old bit.ly link, not an outdated Facebook event ID, not left as plain text).  
3. **Hyperlink text check.** Check every `<a href>` in the draft: the visible text must be words ("here," "click here to join"), never the raw URL. A link where the anchor text is the URL itself is still wrong, even though it's clickable.  
4. **Sign-off check.** Confirm the sign-off reads "Vanessa" as plain text (not a hyperlink), with only the [www.SpeakEnglishWithVanessa.com](http://www.SpeakEnglishWithVanessa.com) line below it as the actual link.

## Names & greetings

- Every reply opens with "Hi \[Name\]," (or "Hi there," only as a last resort) — no exceptions, including template-based replies that show the body starting mid-sentence; the greeting still gets prepended.  
- Contact-form email addresses aren't validated — people mistype them often; this is never the VA's fault, just make a best guess (e.g. "gamil" → "gmail").  
- Many cultures order names family-name-first (Vietnam, Japan, etc.). A quick web search of "\[name\] given name \[country\]" usually clarifies it.

**Priority order for finding the name to use:**

1. A name the student gives themselves in the body of their own reply (e.g., "I'm Cosima," "This is Ali writing") — this outranks everything else, even a conflicting name below, since it's the most authoritative source available.  
2. A name given in the sender's own email signature.  
3. The display name Gmail shows next to the sender's address in the "From" field (e.g., "Merriam [rmmeryem3@gmail.com](mailto:rmmeryem3@gmail.com)") — distinct from the address itself and from the message body.  
4. A name Vanessa's own automated email already used when addressing them (visible in the quoted original).  
5. A reasonable first-name guess parsed from the email address itself.  
6. "Hi there," only when none of the above give anything confident.

Since a human reviews every draft and a wrong guess is an easy fix, prefer a best guess over "Hi there," whenever any signal at all exists — don't fall back to the generic greeting just because the higher-confidence sources came up empty.

## This knowledge base is the authoritative source

Files 00–07 are the current, corrected, accurate state of the business — treat them as authoritative over any older tutorial video, transcript, or FAQ doc in Drive, even where those disagree. If a situation isn't covered anywhere here, tag Vanessa rather than falling back on an older/uncorrected source, so it can get added properly.

## Drafting priority order

**Before checking 06:** if a promo is currently active (see 08-current-promo.md), its pricing, checkout link, and terms override the standard ones in 03 and any stale numbers in 06 or 01, for the exact product and date window stated in file 08\. Promos typically stay honorable for a few days past the official close date (see file 08's "Grace period" field) — check that date, not just the official end date, before falling back to standard terms. If file 08 is empty, absent, or both the end date and any listed grace period have passed, ignore it and fall back to standard pricing/links per 01/03/06 as usual — don't extend an expired promo's terms past its grace period without checking with Vanessa/Ailsa first.

Promos that recur (run more than once a year) have a reusable template saved in the "Promo Library" Google Drive folder (see file 04\) — when one of these runs again, pull the matching template, update the dates, and rebuild file 08 from it rather than starting from scratch.

Check **06-phrase-express-exact-templates.md** first — actual proven wording, use as close to verbatim as possible, customizing only the bracketed parts. If no matching template, check **05-voice-guide-and-additional-scenarios.md** for tone/scenario guidance, then **01-email-response-playbook.md** for broader policy. Always defer to **01/03** for anything price- or product-specific, even when a file 06 template shows an old number — the wording pattern is still good, just swap in the current figure. When a promo is active per file 08, that takes priority over even 01/03's standard figures.

Templates are modular, not all-or-nothing — match the length/content of a reply to what was actually asked, don't send a full four-bullet breakdown for a narrow question.

Watch for templates that assume unverifiable context (e.g. "click the link in the email above," assuming a specific link exists in whatever the student is replying to). When a template depends on account-specific facts that can't be verified, flag it for a human rather than guessing — route to Claude/Need admin.

## Always check the full thread history before drafting

A thread can have multiple back-and-forth messages, including replies Vanessa already sent. Drafting based only on the first/triggering message risks answering a stale question instead of the actual open one. Pull the full thread before drafting and reply to the most recent unanswered message specifically. See file 07 for the technical mechanics of doing this reliably (trashed messages can hide history from a naive fetch, and `update_draft` can silently detach a draft from its thread) and for safe drafting/threading practices.  
