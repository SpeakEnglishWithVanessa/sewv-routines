# SEWV Support Knowledge Base — 02: Admin Task Procedures

These are the exact backend steps a human admin needs to run after certain email replies. When drafting a reply that requires backend action, append a clearly labeled "Admin follow-up" checklist referencing the relevant procedure below, with the specific student's actual details filled in (amounts, tags, dates) — not just a pointer like "see Procedure J."

Tools referenced: Teachable (course platform/LMS), Kit (email marketing — tags \+ sequences \+ automations), Stripe (primary payment processor), PayPal (secondary payment processor).

### Procedure A — Cancel a Monthly Membership

1. Teachable → Users → search student's email → open profile → Purchases tab.  
2. Confirm "Active Subscriptions" is showing.  
3. Three-dot menu → Delete Subscription → confirm Yes.  
4. Kit → Subscribers → search email → open profile → Tags.  
5. Delete the relevant membership tag(s) — most common "FFC 3.0" / "FFC Purchased" (Monthly), or "FFC: Yearly."  
6. Add the cancel tag (e.g. "FFC cancel").  
7. System auto-sends the student a cancellation confirmation shortly after.

### Procedure B — Monthly failed-payment cleanup (currently automated via Zapier, testing)

A Zapier automation removes the membership tag automatically after a 3rd failed payment attempt. Manual fallback procedure (Teachable export → Kit import → segment by "has membership tag but not in this month's success import" → strip the tag) is kept on file in case the automation needs to be reverted to manual.

### Procedure C — First-of-the-month module unlock (discontinued)

No longer used — all modules are available to every Monthly/Yearly/Lifetime student automatically. If a student can't find the current module, send the 2026 Study Plan doc link: [https://drive.google.com/file/d/1RQmK\_z48Y83lfJxSoP\_GxJgfqzi5nmmh/view?usp=sharing](https://drive.google.com/file/d/1RQmK_z48Y83lfJxSoP_GxJgfqzi5nmmh/view?usp=sharing)

### Procedure D — Misspelled email address, during Teachable business hours (M–F, \~8/9am–5pm)

1. Check what address they actually sent the email from — often the real one. Search Teachable first with that address or a partial guess (Teachable's search often surfaces a close match from a fragment). Only if empty, check Kit; only if that's empty too, check Stripe.  
2. Teachable → student profile → Information tab → correct the spelling → Save (doesn't auto-send a confirmation).  
3. Email Teachable Support to manually resend the confirmation.

### Procedure E — Misspelled email address, after hours / self-service

1. Visit [https://speak-english-with-vanessa.teachable.com/sign\_in](https://speak-english-with-vanessa.teachable.com/sign_in) → "Forgot password."  
2. Enter the (corrected) email address.  
3. Password-reset email → set new password → log in.  
4. A red banner should prompt "confirm your email" with a Resend link — have them click it.

### Procedure F — Cleaning up a duplicate/bounced Kit entry from a misspelling

1. Search Kit for the incorrect spelling.  
2. If bounced/undelivered with no legitimate tags, delete that entry.  
3. Re-apply the correct tag(s) on the primary entry. Teachable accounts can't be merged — if a student ends up with two real paid accounts, refund one or accept the duplicate.

### Procedure G — Unbounce a subscriber in Kit

1. Confirm the orange "Bounce" status in Kit.  
2. Contact Kit support: "This subscriber has been bounced — can you please un-bounce them?"  
3. Email Teachable Support to resend the confirmation once un-bounced.  
4. Consider manually enrolling in the meantime if the bounce clearly wasn't their fault.

### Procedure H — Troubleshoot "I unsubscribed but got charged"

1. Teachable → confirm charge date/amount.  
2. Kit → check unsubscribe date and whether the paid-membership tag is still present.  
3. Common cause: they unsubscribed from the newsletter, not the paid membership.  
4. If so, run Procedure A and refund the specific erroneous charge (Teachable if within 30 days, otherwise Stripe/PayPal directly).

### Procedure I — Stripe payment dispute/chargeback notice

We no longer contest disputes. Delete/ignore the notification — no evidence submission. Only follow-up: if the dispute is about the Monthly Membership, confirm in Teachable the subscription is actually canceled; if still active, delete it (Procedure A). Per playbook entry \#12, this verification step is now skipped entirely for customer-facing routing — every dispute notice goes straight to Claude/Need deleted regardless.

### Procedure J — Refund via PayPal (30+ days old, or paid via PayPal)

1. PayPal → Activity → All Transactions → search by name (widen date range if needed).  
2. Open the payment → Refund → enter amount → Issue Refund.  
3. PayPal auto-emails a confirmation — no manual notification needed.  
4. Still complete the Teachable side: delete subscription/enrollment, confirm Kit tags.

### Procedure K — Special-case refunds outside the normal 30-day window

Default: approve it, especially for hardship — cheaper than a later dispute.

1. Teachable → delete the subscription/enrollment.  
2. Stripe → refund the specific payment(s) requested (leave an internal note on which months).  
3. Kit → confirm the cancel tag; unsubscribe from sales emails only if it seems kind, not automatic.  
4. Escalate to Vanessa/Ailsa first if: 6–12+ months old, heavy usage, no clear reason — possible refund-abuse pattern.

### Procedure L — Grant full/early access to a challenge

1. Teachable → student profile → Enrollments tab.  
2. Find the enrollment → three-dot menu → Grant Full Access → confirm.  
3. Evergreen/self-paced courses: no restriction, always fine. Live/date-bound courses: fine once the official start date has passed.

### Procedure M — Manually enroll in this month's module (discontinued)

No longer needed — everything is automatic. If a student can't find the current module, send the 2026 Study Plan link (see Procedure C) or tell them to search by module name after logging in.

### Procedure N — Create a personalized one-time coupon code

Standing exception needing no approval: the Lifetime loyalty discount (see playbook \#15). Everything else needs Vanessa/Ailsa confirmation first.

1. Once approved: Teachable → Courses → the product → Coupons → Create Coupon.  
2. Discount amount/percentage. Single-use depends on what's discounted, not a blanket default:  
   - One-time purchase (Lifetime): single-use.  
   - Yearly subscription: must apply to **all payments**, not just first year — select "applies to all payments" in Teachable's coupon settings, don't mark it single-use.  
   - Payment plan (Lifetime's 4-month plan): applies across all installments.  
3. Set an expiration date matching what was offered.  
4. Send the checkout link with the coupon embedded (see Procedure Q).

### Procedure O — Unsubscribe / Resubscribe in Kit

Unsubscribe: click "Unsubscribe from all" on the subscriber's Kit profile. Resubscribe: click "Resubscribe" → confirm — only with explicit consent/request. If unsubscribed 6+ months, the cleanest path is often a fresh lead-magnet signup (auto re-adds to the newsletter); otherwise Kit support can manually resubscribe (keep written consent on file first).

### Procedure P — "Safe Unsubscribe" bounce-back handling

Auto-generated notices (often French) that someone's own unsubscribe click failed. Open the email, click the direct link (routes to unsubscribing in Kit). If the link doesn't work, manually search their email in Kit and unsubscribe directly.

### Procedure Q — Add a coupon code directly to a checkout link

1. Copy the product's pricing-plan (checkout) URL, not the sales page.  
2. Open in an incognito tab.  
3. Append `&couponcode=CODENAME` — don't press Enter yet.  
4. Copy the full URL as-is — this goes in the student email.  
5. Then press Enter in the incognito tab to confirm the discounted price actually shows correctly before sending.

---

**Note on trust in automation:** Zapier syncs Teachable ⇄ Kit tags automatically (e.g. a Teachable cancellation should auto-remove the Kit tag), but this is known to occasionally miss people — always manually double-check the Kit side after any Teachable change (cancel, refund, enroll).  
