# Handled. — Transactional & Lifecycle Emails

**What this is:** Copy for the automated emails Handled. sends — welcome, trial
reminders, payment issues, backup nudges, win-back. Same brand, applied to the inbox.
Follows [`docs/voice-and-tone.md`](../voice-and-tone.md) and mirrors the in-app copy in
[`docs/in-app-microcopy.md`](../in-app-microcopy.md).

**House style for email** (a deliberate brand choice):
- **These look like a real person wrote them, because one did.** Handled. was built by
  a practicing commercial litigator. Emails are **plain-text, founder-signed**, not
  designed marketing blasts. That *is* the brand — "be who you say you are" (Principle 3).
- **One idea, one link.** A single clear CTA per email. No link farms, no footer of
  cross-sells.
- **Subjects are calm and honest** — never clickbait, fake urgency, or emoji-as-energy.
  A subject should read like a note from a colleague.
- **Never fabricate.** No "join thousands of attorneys," no invented urgency. We're
  pre-launch and we say so. Founding-rate scarcity is real (first 200) and only stated
  when true.
- Replace `{Founder}` with the founder's real name/signature, `{first_name}`,
  `{date}`, `{price}`, etc. If `{first_name}` is unknown, drop the greeting to a plain
  "Hey there —" rather than guess.
- Every email a real human might reply to should come **from a monitored, real reply-to
  address** — replies are a gift (Principle 4: treat criticism as customers caring).

### Delivery setup (Resend — verified as of this writing)

- **Sending domain:** `legalhandled.com` — verified in Resend, sending enabled
  (us-east-1). Send from a real, human `from` address on this domain (e.g.
  `{founder}@legalhandled.com`), not a `no-reply@`. A no-reply address contradicts the
  whole house style.
- **Reply-to:** Resend *receiving* is disabled on the domain, so replies won't land in
  Resend. Point `reply-to` at a real monitored mailbox (Google Workspace, etc.) so the
  "just reply, I read these" promise is true.
- **Auth/system mail** already flows through Resend via the "Supabase SMTP" key; these
  lifecycle emails are separate and should send under their own clearly-named key.
- **Open/click tracking is off** on the domain — keep it that way unless there's a real
  reason; it suits the plain-text, personal-note style.

---

## 1. Welcome — new Free account

**Subject:** You're on Handled. Here's what that means.
**Preview:** Free, forever. Your data stays on your device.

> Hey {first_name} —
>
> You're in, on the Free tier — and Free means free. No time limit, no card, no
> auto-conversion. If it does everything you need, stay here as long as you like.
>
> Two things worth knowing on day one:
>
> - **Your case data lives on your device**, in a local database. Nothing goes to a
>   cloud or a server we run. It's yours.
> - **Back it up early.** One click captures every matter, note, and date in a single
>   file you keep. If a laptop ever dies, you restore and you're right back where you
>   were.
>
> The fastest way to feel it: open your first matter. The dashboard fills in from there.
>
> I built this because the software I had to use was made for every kind of lawyer,
> which meant it fit none of us. If something doesn't map to how litigation actually
> moves, tell me — just reply. I read these.
>
> — {Founder}
> Built Handled. · still practicing
>
> `Open your first matter →`

---

## 2. Onboarding nudge — signed up, no matter yet (day 2, only if empty)

**Subject:** Your board's still empty
**Preview:** One matter and it starts working for you.

> Hey {first_name} —
>
> Noticed you haven't opened a matter yet — no pressure, just want to make sure nothing's
> in your way.
>
> A matter is the whole case on one page: parties and counsel, key dates, court and
> department, notes. Add one and every deadline on it starts showing up on the dashboard,
> ranked by urgency, with a live countdown.
>
> Takes about two minutes. If something's stopping you, reply and tell me what — that's
> useful to me.
>
> — {Founder}
>
> `Add your first matter →`

---

## 3. Trial started — Pro trial

**Subject:** Your Pro trial is on
**Preview:** 30 days of the full practice. No charge until {trial_end_date}.

> Hey {first_name} —
>
> Your 30-day Pro trial just started. That opens up the full practice:
>
> - A unified **calendar** — every deadline and appearance, color-coded by urgency
> - **Negotiation tracking** — demands, offers, and counters logged in the matter
> - **Stage checklists and timelines** — so nothing gets skipped on the way to trial
>
> No charge until **{trial_end_date}**, and I'll remind you before that date — no
> surprise bill. Cancel anytime and you drop to Free with every matter intact.
>
> — {Founder}
>
> `Set up your calendar →`

---

## 4. Trial reminder — 3 days left

**Subject:** 3 days left on your trial
**Preview:** Here's exactly what happens on {trial_end_date}.

> Hey {first_name} —
>
> Quick heads-up so nothing catches you off guard: your Pro trial ends **{trial_end_date}**.
>
> Here's exactly what happens that day:
>
> - **Staying on Pro?** Nothing to do. Your founding rate of **${price}/mo** begins —
>   locked in for as long as you stay, even after the founding program closes.
> - **Prefer Free?** Switch anytime before then. You keep every matter you've entered;
>   only the Pro views go quiet.
>
> Either way, your data is yours and nothing gets deleted.
>
> — {Founder}
>
> `Manage my plan →`

---

## 5. Trial ending — tomorrow

**Subject:** Your trial ends tomorrow
**Preview:** No surprises — just so you know.

> Hey {first_name} —
>
> Your Pro trial ends tomorrow, **{trial_end_date}**. After that you move to Pro at your
> founding rate of **${price}/mo**, locked in as long as you stay.
>
> If Pro's earning its place, you don't need to do a thing. If you'd rather go back to
> Free, switch here in a few seconds — your matters come with you either way.
>
> — {Founder}
>
> `Keep Pro or switch to Free →`

---

## 6. Trial ended → moved to Free (no card on file)

**Subject:** You're on Free — nothing was charged
**Preview:** Every matter's still here. Pro's paused, not gone.

> Hey {first_name} —
>
> Your trial wrapped and you weren't charged — you didn't have a card on file, so we'd
> never bill you by surprise.
>
> You're on Free now. **Every matter you entered during the trial is still here.** The
> Pro views — calendar, negotiations, stage timelines — are paused, not deleted. They
> switch right back on if you upgrade later.
>
> No rush. Upgrade when the caseload demands it, not before.
>
> — {Founder}
>
> `See what Pro adds →`

---

## 7. Payment succeeded — receipt

**Subject:** You're on {plan}. Handled.
**Preview:** Founding rate locked in. Receipt below.

> Hey {first_name} —
>
> You're on **{plan}**, at your founding rate of **${price}/mo** — locked in for as long
> as you stay.
>
> Receipt:
> - Plan: {plan}
> - Amount: ${price}
> - Date: {date}
> - Next renewal: {next_date}
>
> Manage or cancel anytime from your account — no hoops. Thanks for betting on something
> early. I don't take that lightly.
>
> — {Founder}
>
> `View my account →`

---

## 8. Payment failed — first notice (day 0)

**Subject:** That payment didn't go through
**Preview:** Nothing changed yet. Usually a quick card fix.

> Hey {first_name} —
>
> Your **{plan}** payment was declined. It's almost always something small — an expired
> card or a routine bank hold — not anything on your end to worry about.
>
> Nothing's changed yet: you're still on {plan} and **your matters are untouched**.
> Update your card and we'll retry automatically.
>
> — {Founder}
>
> `Update my card →`

---

## 9. Payment failed — final notice (day 5)

**Subject:** Heads-up before your plan changes
**Preview:** Your data's safe either way. Here's what's next.

> Hey {first_name} —
>
> We've tried your card a couple more times and it's still not going through. On
> **{grace_end_date}**, if it hasn't cleared, your account moves to **Free**.
>
> What that means, plainly:
>
> - **Nothing is deleted.** Every matter, date, and note stays on your device.
> - The Pro views just pause until billing's sorted.
> - You can update your card anytime and pick right back up at your founding rate.
>
> No penalty, no lockout of your data — that's yours no matter what.
>
> — {Founder}
>
> `Update my card →`

---

## 10. Backup reminder — behavioral nudge

*Trigger: no backup created in {N} days (and there's data to lose). Send sparingly —
at most one every couple of weeks.*

**Subject:** You haven't backed up in a while
**Preview:** One click, and a dead laptop stops being a disaster.

> Hey {first_name} —
>
> Not nagging — just watching your back. It's been about {N} days since your last backup,
> and you've added matters since.
>
> Because your data lives on your own device (the way it should), a backup is what turns
> a lost or dead laptop from a catastrophe into a five-minute restore. One click captures
> everything into a single file you keep wherever you want.
>
> — {Founder}
>
> `Back up now →`

---

## 11. Win-back — after cancellation (send later, once, low-key)

**Subject:** Your matters are right where you left them
**Preview:** No pitch. Just so you know it's here.

> Hey {first_name} —
>
> No pitch here. Just a note that everything you built in Handled. is still exactly where
> you left it, and Pro turns back on the moment you want it — every matter, date, and note
> intact.
>
> If your founding rate is still open, it's yours when you come back. And if Handled.
> wasn't right for how you work, I'd genuinely value a reply telling me why. That's how
> it gets better.
>
> — {Founder}
>
> `Pick up where I left off →`

---

## Pre-send checklist

Run the voice checklist on every email before it ships:

**Calm? True? Tight? Insider? On their side? Sounds like Handled.?**

Plus two email-only checks:
- **One CTA?** Exactly one thing to do.
- **Would a real litigator believe a person wrote this?** If it smells automated, rewrite
  until it doesn't.
