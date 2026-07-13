# Handled. — In-App Microcopy

**What this is:** Ready-to-use copy for the in-app surfaces where a marketing voice
usually drifts — empty states, errors, confirmations, and the billing/cancellation
flow. All of it applies [`docs/voice-and-tone.md`](voice-and-tone.md): calm, honest,
concise, litigation-fluent, on the attorney's side.

**Grounding facts** (from the product): storage is **local-first** — a database on the
attorney's own device, no cloud sync. Backup/restore is a **local file the user
chooses**, plus **CSV import/export**. Runs on **macOS + Windows**, offline. Tiers are
**Free (forever) / Solo ($14/mo) / Pro ($29/mo)** with a **30-day trial** and
**founding rates for the first 200 attorneys.** Copy must never reference a "server"
or "cloud" for the attorney's case data — that would contradict the promise.

**Conventions:** `[Heading]`, then body text, then buttons shown as `Primary` /
`Secondary`. Italics mark the payoff word. Swap `{matter}`, `{count}`, `{date}` etc.
for real values.

---

## 1. Empty states

Empty states are a first impression, not an error. Name what's missing, point to the
one next action, and stop.

**Dashboard — no matters yet**
> `[Nothing on the board yet.]`
> Add your first matter and your caseload starts filling in — deadlines ranked by
> urgency, appearances, the whole file.
> `Add your first matter`

**Deadlines — none outstanding (all clear)**
> `[Nothing due. _That's the goal._]`
> Every deadline across your matters is accounted for. When something's coming, it
> shows up here first — ranked by urgency, with a live countdown.
> `View all matters`

**Matters list — empty**
> `[No matters yet.]`
> A matter holds everything about a case: parties and counsel, key dates, court and
> department, client details, notes. Start one and it stays current for the life of
> the case.
> `Add a matter`

**Matter detail — no key dates**
> `[No key dates on this matter.]`
> Add a deadline or an appearance and it joins the timeline — and the countdown
> starts.
> `Add a key date`

**Matter detail — no parties**
> `[No parties added.]`
> Add the parties and their counsel so the whole case is on one page when you need it.
> `Add a party`

**Timeline — empty**
> `[The timeline builds itself.]`
> As you add deadlines, actions, and appearances, they line up here in order — what's
> behind you, what's today, what's next.
> `Add the first date`

**Calendar — nothing this month** *(Pro)*
> `[A clear month.]`
> No deadlines or appearances scheduled. Anything you add across your matters lands
> here, color-coded by urgency.

**Negotiations — nothing logged** *(Pro)*
> `[No offers logged yet.]`
> Keep demands, offers, and counters in the matter itself — not a spreadsheet you'll
> have to go find later.
> `Log an offer`

**Stages — no checklist started** *(Pro)*
> `[No stage checklist yet.]`
> Turn on stage checklists and nothing gets skipped on the way to trial.
> `Set up stages`

**Appearances — none upcoming**
> `[No appearances on the calendar.]`
> When you have a hearing or conference, it shows here with the matter one click away —
> so you never walk in cold.
> `Add an appearance`

**Search — no results**
> `[No matches for "{query}".]`
> Try a party name, a case name, or a court. Search covers every matter you've entered.

**Backups — none yet**
> `[No backups yet.]`
> A backup captures every matter, note, date, and client record in a single file you
> keep. Takes one click.
> `Create a backup`

---

## 2. Errors & recovery

The rule that matters most: when a matter or a deadline is at stake, **never be flip.**
Say plainly what happened, reassure them their data is safe, and give the next step.
No error codes as the headline, no "oops," no blame.

### Data & files

**Save failed (write error)**
> `[That change didn't save.]`
> Your matter is intact — we just couldn't write the last edit to the database. Try
> again. If it keeps happening, restore from your most recent backup.
> `Try again` / `Open backups`

**Backup failed**
> `[The backup didn't finish.]`
> Nothing was lost and your matters are untouched — the backup file just didn't write.
> Check that the folder you chose has space and try again.
> `Try again` / `Choose a different folder`

**Restore — invalid or corrupt file**
> `[This file can't be restored.]`
> It doesn't look like a Handled. backup, or it's incomplete. Your current data hasn't
> changed. Pick a different backup file to restore from.
> `Choose another file` / `Cancel`

**Restore — confirm overwrite** *(destructive)*
> `[Restoring replaces what's here now.]`
> This will replace your current data with the backup from **{date}**. Anything added
> since then won't carry over. Want to back up the current state first?
> `Back up, then restore` / `Restore now` / `Cancel`

**CSV import — malformed file**
> `[We couldn't read that CSV.]`
> The columns don't match what Handled. expects. Nothing was imported and your matters
> are unchanged. Download the template, match your columns, and try again.
> `Download template` / `Choose another file`

**CSV import — partial success**
> `[Imported {success} of {total} rows.]`
> {failed} rows were skipped — usually a missing case name or an unreadable date.
> Everything that imported is already in your matters. Review the skipped rows and
> re-import just those.
> `Review skipped rows` / `Done`

**Database locked / already open**
> `[Handled. is already running.]`
> Your case data can only be open in one place at a time — that's what keeps it from
> getting crossed up. Switch to the open window, or close it and reopen here.
> `Got it`

**Disk full / no space**
> `[Not enough room to save.]`
> Your device is out of storage, so the last change couldn't be written. Your existing
> matters are safe. Free up some space and try again.
> `Try again`

**Unexpected error (fallback)**
> `[Something went wrong there.]`
> Your data is safe on your device. Try that again — if it keeps happening, a backup
> and restart usually clears it, and you can send us the details.
> `Try again` / `Send details`

### Validation (inline, not alarming)

- **Deadline set in the past:** "That date's already passed. Save it anyway, or pick a
  new one?" → `Save anyway` / `Change date`
- **Missing case name:** "A matter needs a case name to file under."
- **Missing required field:** "Add {field} to save this matter."
- **Duplicate matter:** "You already have a matter named "{name}." Open it, or create a
  separate one?"

### Destructive confirmations (clear, never guilt-trippy)

**Delete a matter**
> `[Delete "{matter}"?]`
> This removes the matter and everything in it — parties, dates, notes — from this
> device. It can't be undone. If you might want it later, export it to CSV first.
> `Export, then delete` / `Delete` / `Keep it`

**Delete a deadline**
> `[Remove this deadline?]`
> It comes off the dashboard and the timeline. You can add it back anytime.
> `Remove` / `Keep`

### Licensing & connection (billing only — never case data)

**License check — offline**
> `[Can't reach us to confirm your plan.]`
> Handled. keeps working offline — your matters don't need a connection. We just
> couldn't verify your subscription right now, so we'll check again automatically.
> Nothing to do.
> `Got it`

**Activation failed**
> `[We couldn't activate your plan.]`
> Your data is fine and Free keeps working. This is a billing hiccup, not a data one.
> Check your connection and try again, or we'll help you sort it.
> `Try again` / `Contact us`

---

## 3. Success & confirmations

Quietly satisfying. Confirm and get out of the way — no confetti. Save the brand's
signature "_It's handled._" for moments that have actually earned relief.

- **Matter created:** "Matter opened. It's on the board."
- **Backup created:** "Backed up. Every matter, in one file — right where you chose it."
- **Restore complete:** "Restored. You're back exactly where you left off."
- **CSV export complete:** "Exported. Your matters are in a CSV you own — never locked in."
- **Deadline added:** "Added. The countdown's running."
- **Appearance added:** "On the calendar. You won't walk in cold."
- **All deadlines clear (state, not a toast):** "Nothing due. _It's handled._"

---

## 4. Billing, trials & cancellation

Gracious, plain, and friction-free — this is Principle 4 (*do the right thing*) where
customers are most cynical about software. No dark patterns, no guilt, no buried terms.

**Trial started**
> `[Your 30-day Pro trial is on.]`
> The full practice — unified calendar, negotiation tracking, stage checklists. No
> charge until **{trial_end_date}**, and we'll remind you before then. Cancel anytime
> and you'll drop to Free with every matter intact.
> `Start using Pro`

**Trial ending — 3 days out**
> `[3 days left on your Pro trial.]`
> On **{trial_end_date}** your founding rate of **${price}/mo** begins — locked in for
> as long as you stay. Nothing to do if you're staying. Prefer Free? Switch now and
> keep everything you've entered.
> `Keep Pro` / `Switch to Free`

**Trial ending — day before**
> `[Your trial ends tomorrow.]`
> Tomorrow you move to Pro at your founding rate of **${price}/mo**. Change your mind
> anytime — Free is always there, and your matters come with you either way.
> `Keep Pro` / `Switch to Free`

**Trial ended → downgraded to Free (no card on file)**
> `[You're on Free.]`
> Your trial wrapped and you weren't charged. Every matter you entered is still here.
> The Pro views — calendar, negotiations, stage timelines — are paused, not deleted.
> Upgrade whenever the caseload calls for it.
> `See Pro` / `Keep going on Free`

**Payment succeeded**
> `[You're on {plan}. _Handled._]`
> Founding rate of **${price}/mo**, locked in for as long as you stay. Receipt's on its
> way to {email}.
> `Back to work`

**Payment failed (card declined)**
> `[That payment didn't go through.]`
> Your card was declined — it happens, often just an expiry or a bank hold. Nothing
> changed on your account and your matters are untouched. Update your card and we'll
> try again.
> `Update card` / `Remind me later`

**Upgrade (Free/Solo → higher)**
> `[Move up to {plan}?]`
> Adds {feature summary}. Your founding rate of **${price}/mo** is locked in as long as
> you stay, and everything you've entered carries straight over.
> `Upgrade` / `Not yet`

**Downgrade (Pro → Solo / Solo → Free)**
> `[Switch to {plan}?]`
> You keep every matter, date, party, and note — nothing is deleted. The {higher-tier}
> views just go quiet until you come back. The change takes effect at your next billing
> date, **{date}**.
> `Switch to {plan}` / `Stay on {current}`

### Cancellation flow

One honest screen. The primary action respects their choice; no interstitial
guilt-trap.

**Step 1 — Cancel screen**
> `[Cancel your {plan} plan?]`
> Straight answers, since that's how we do this:
> - **Your data stays yours.** Every matter, note, and date remains on your device.
>   Export it all to CSV anytime.
> - **Free keeps working.** You'll move to the Free tier — no time limit, no card.
> - **Nothing's deleted.** Pro views pause; they're right where you left them if you
>   come back.
> - **You keep access until {period_end}**, the end of the period you've paid for.
>
> `Export to CSV first` / `Cancel my plan` / `Never mind, keep it`

**Step 2 — Optional, one question (skippable)**
> `[Anything we could've handled better?]`
> Optional — but if something fell short, we'd genuinely like to know. We read every
> one.
> `[ short text field ]`
> `Send & cancel` / `Skip & cancel`

**Step 3 — Cancellation confirmed**
> `[Done. You're on Free as of {period_end}.]`
> No further charges. Your matters are all still here, and your CSV export is available
> whenever you want it. If Handled. earns its way back into your practice, your matters
> will be waiting exactly as you left them.
> `Back to my matters`

**Win-back (later, low-key — not nagging)**
> `[Your matters are right where you left them.]`
> Whenever the caseload gets loud again, Pro turns back on with everything intact — and
> if your founding rate is still open, it's yours.
> `See what's new` / `No thanks`

---

## Before it ships — the 30-second checklist

From the voice guide: **Calm? True? Tight? Insider? On their side? Sounds like
Handled.?** If any answer is no, it's not handled yet.
