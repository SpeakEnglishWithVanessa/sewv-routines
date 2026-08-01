# SEWV Support Knowledge Base — 00: Overview & Workflow

Source: Ailsa's VA training tutorials, compiled July 2026; corrected and expanded through direct sessions with Claude, July 27–30, 2026\.

## The business

Speak English With Vanessa (SEWV) sells English-fluency courses (the "Fearless Fluency Club" and related challenges) via Teachable, with email marketing/automation on Kit, and payments through Stripe (primary) and PayPal (secondary).

## Team & roles

- **Vanessa** — owner/instructor. Final say on judgment calls, non-standard discounts, and anything unusual (6–12+ month old refund requests, ambiguous collab offers, etc.)  
- **Ailsa** — senior VA / trainer. Day-to-day inbox lead; will be rewriting drafts herself once the inbox is handed over, without a review layer in between — so drafts need to be correct the first time, not just correctable.  
- **Amber** — English-content teacher. Handles grammar/pronunciation-specific student questions.  
- **Norah** — VA; works weekends and fills in when Ailsa is away.  
- **Laura** — copywriter/PM with delegated inbox access; role in flux as of late July 2026\.

Team members communicate by emailing/tagging each other directly, or by creating a draft and tagging the intended reader via the Gmail label system. Always start "Hi \[Name\]" and sign your own name.

## Scope: only act on activity from the last 30 days

The daily "check email" workflow only applies to threads with activity within the past 30 days. The inbox has years of old, already-resolved, or personal/internal threads that were never cleared out (old collab threads, invoices, hiring correspondence, etc.) — these are out of scope entirely. Don't label, draft, or otherwise touch anything older than 30 days. This applies to every source (general inbox, SEWV Newsletter label, etc.) and every destination. If old backlog needs cleaning up, that's a separate, explicitly-requested project.

## The general/main inbox and spam folder

The **general inbox** (no label applied) is mostly people who typed Vanessa's email address directly, or replied via the website contact form — not meant to be a strictly filtered view. **Spam folder**: checked occasionally, not routinely; empty it monthly after checking. Other Gmail system tabs (Updates, Promotions, etc.) already have their own filters — no need to check separately.

## Inbox goals

- Empty the inbox every day; respond within 24 hours.  
- Lower-priority emails can wait a couple of days.  
- Delete an email after responding, unless keeping it for reference.  
- Busiest periods: last week/first days of each month, and any promo or challenge launch.

## Priority system

**High priority** (1–2 days): current students/paying customers; people likely to become customers (real interest, real questions); payment issues, signup errors, broken links; anyone tagged to you by a teammate.

**Low priority** (2–3+ days fine): people unlikely to ever become customers just asking general questions; threads needing a reply but not urgent.

**Safe to delete without a reply — the majority of the inbox.** See 01-email-response-playbook.md entry \#21 and the recalibration rule there for the full, current criteria — this list has been significantly tightened since the original version of this file, so defer to file 01 rather than an older mental model of what counts as "worth a reply."

## Standard email format

**Links**: insert as hyperlinked text ("click here to join," "here's the link"), not a raw pasted URL, in every draft — via `htmlBody` with a real `<a href>` tag. Gmail wraps every outgoing link in its own click-tracking redirect regardless of formatting; that's normal, not something wrong with the draft — the fix is only about what text is visible to the reader.

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

Footer link: text reads exactly [**www.SpeakEnglishWithVanessa.com**](http://www.SpeakEnglishWithVanessa.com), hyperlinked to [https://www.SpeakEnglishWithVanessa.com](https://www.SpeakEnglishWithVanessa.com) (plain text body: no raw `https://` in front, to avoid Gmail's own tracking-wrapper).

Other notes:

- If mid-thread with someone (several emails already exchanged), a shorter "Thanks for your email" is fine instead of the full opener.  
- Prefer plain, simple wording ("can" instead of "are able to") — most recipients are English learners. Avoid idioms/advanced phrases (e.g. "ease up") — don't try to rephrase them, just cut the sentence rather than keep an idiom in a different form.  
- Capitalize course names as proper nouns: "the Fearless Fluency Club," "the Monthly Membership."  
- No em dashes in student-facing content — use a comma or colon instead. Internal notes/checklists can still use dashes.  
- One sentence per line reads better for ESL readers in promotional/marketing copy; standard support replies stay in normal paragraph form.

## Grammar: comma-splice self-check — required before finalizing every draft

Comma splices (two independent clauses joined only by a comma, no conjunction) are the most common recurring error. Before finalizing any draft, re-read every sentence and test each comma: cover up everything before it and everything after it — if both halves could stand alone as a full sentence, it's a splice. Fix with a period \+ capital letter, a coordinating conjunction (and/but/so/or), or a semicolon if the clauses are closely related. This is a distinct final pass, not just something to keep in mind while writing.

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

Files 00–06 are the current, corrected, accurate state of the business — treat them as authoritative over any older tutorial video, transcript, or FAQ doc in Drive, even where those disagree. If a situation isn't covered anywhere here, tag Vanessa rather than falling back on an older/uncorrected source, so it can get added properly.

## Drafting priority order

Check **06-phrase-express-exact-templates.md** first — actual proven wording, use as close to verbatim as possible, customizing only the bracketed parts. If no matching template, check **05-voice-guide-and-additional-scenarios.md** for tone/scenario guidance, then **01-email-response-playbook.md** for broader policy. Always defer to **01/03** for anything price- or product-specific, even when a file 06 template shows an old number — the wording pattern is still good, just swap in the current figure.

Templates are modular, not all-or-nothing — match the length/content of a reply to what was actually asked, don't send a full four-bullet breakdown for a narrow question.

Watch for templates that assume unverifiable context (e.g. "click the link in the email above," assuming a specific link exists in whatever the student is replying to). When a template depends on account-specific facts that can't be verified, flag it for a human rather than guessing — route to Claude/Need admin.

## Always check the full thread history before drafting

A thread can have multiple back-and-forth messages, including replies Vanessa already sent. Drafting based only on the first/triggering message risks answering a stale question instead of the actual open one. Pull the full thread before drafting and reply to the most recent unanswered message specifically. See file 07 for the technical mechanics of doing this reliably (trashed messages can hide history from a naive fetch) and for safe drafting/threading practices.

# **SEWV Knowledge Base — Amendment to 00-overview-and-workflow.md**

Added August 2026\. Insert into 00-overview-and-workflow.md, near the top (e.g. after "The business" or as its own section).

## **Preferred reference-file format: Markdown**

Upload the .md version of each numbered knowledge base file (00-07) when available, in addition to or instead of the .docx version. Reading a plain .md file is a direct read with no extraction step; reading a .docx requires unzipping and parsing the internal XML (or a LibreOffice conversion), which costs extra time and tool calls. If both a .docx and .md version of the same file exist, the .md version should be treated as the source of truth and read first.

## **Inbox goals — updated**

Empty the inbox every day; respond within 24 hours. This is now a hard requirement, not a target: at the end of any "check email" pass, zero threads should remain sitting in the inbox unlabeled. Every thread gets a label of some kind — there is no "leave it for later, untouched" outcome anymore. See the updated labeling rule in 04-tools-glossary-and-open-items.md for exactly how ambiguous-but-important threads should be routed instead of left bare.

