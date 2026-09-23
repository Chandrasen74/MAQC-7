# PERSISTENT MEMORY

## Environment & tooling
- Repo: `/home/user/MAQC-7`, flat layout. Use the branch required by the current Arena session instructions; never hardcode an earlier session branch.
- `git` + `gh` pre-authed. Shallow clone; default refspec tracks `origin/main` only.
  Fetch other branches explicitly (`git fetch origin <branch>` → FETCH_HEAD).
- Python: `pypdf` does NOT survive sandbox resets → reinstall via
  `pip install -q --break-system-packages pypdf` when PDF extraction is needed.
- **Persistence model (verified Sep 16): each turn may run in a fresh container where ONLY
  pushed git state is restored.** `~/.agent/` and any uncommitted work can vanish between turns.
  Canonical memory lives in repo `.agent/` (committed); mirror to `~/.agent/` when needed. If local HEAD sits on f96e894 with a full worktree, the container was reset: fetch, diff worktree vs remote tip, mixed-reset to tip if identical, then continue.

## MAQC S7 domain facts (confirmed)
- Weekly rhythm: MM list Monday → lock time before **Fri 6:00 AM UTC** → play + submit before **Sun 6:00 AM UTC**.
- Format: Bo3 CPC on weekly map. Screenshots of EVERY game, posted in battle post by winner.
- **Equalize with bots, always** (mod-confirmed 14 Sep — overrides Info Guide's Fill-or-Equalize line).
- BOT matchups: must play + submit (else loss); full Bo3; no locked time needed; **even 1 human can run it**.
- Week 5: **#665 vs BOT** · Forbidden City · Bracket 10 (⚠️ same # as W4 — always say "Week 5"). ✅ 2-0 (15 Sep, Stefania-recorded).
- W5 deadlines: submit by Sun 20 Sep 6:00 AM UTC `<t:1789884000:F>`. Fri cutoff irrelevant (no opponent).
- W2 #671 precedent: ranges ≠ agreement; need one exact UTC + yes from both sides or both take an L.
- Channels: `#s07-mm-list` · `#s07-battle-posts-week-0X` · `#maqc-support-leaders` (tickets).
- Mod contact: night fury (`<@934544234000830525>` — confirmed by reply screenshot 16 Sep;
  earlier "mikeyyy" label was a chat-export parse error, corrected). Ping ONE active mod at a time.
- Conversions: IST = UTC+5:30 · EDT = UTC−4 · Sat 19 Sep 4:00 PM UTC = `<t:1789833600:F>`.
- W4 postscript: ZiM DM'd accusations (Sep 16) about "hiding behind rules" — baseless, match was played.
  Playbook: one calm reply, disengage, misconduct ticket only if harassment continues.
- Roster health → RESOLVED (20 Sep night): Destroyer + Baby Bird sent no reply by the 10:00 PM IST
  team deadline → counted out; night fury REMOVED both himself (ticket #583, 10:49 PM IST, captain
  supplied IDs 67665771 + 26410318) and updated the team max SP. Final roster: captain + Gunshot +
  Bowolf (3; mod min 2). Sat 19 Sep practice happened; Gunshot attended. Gunshot's W6 commitment
  still unconfirmed.
- SP discrepancy → RESOLVED (20 Sep night, ticket #583): mod had first set 20,723 in error; captain
  flagged with teammate's 22,700 + screenshot → mod raised it. **Team max SP = 22,700 confirmed.**
  Mods read SP MANUALLY ("max sp in the person's hangar at the time we check") — values can drift;
  automation suggestion relayed to mod. Ticket #583 CLOSED. Bracket 10 re-verify on W6 MM PDF.
- **mikeyyy_007 = night fury's username** (same person — captain-confirmed 20 Sep). Earlier "mikeyyy"
  chat-export label was a parse error, coincidental. night fury verified ID `<@934544234000830525>`.
  "Stain" (Stefania?) = another mod/organizer the captain has discussed SP automation with (role unconfirmed).
- Mid-season roster changes: RESOLVED by night fury ruling 20 Sep (Ticket #583, verbatim in KB):
  removal allowed anytime, no penalty, team can't drop below 2, SP recalc possible if removed player
  was highest SP; remove BEFORE the week's MM for even pairing (during week = uneven pair).
  Pre-15-Aug penalty-free registration window still stands (pre-season only).
- Week 6 MM list drops Mon 21 Sep 2026 6:00 AM UTC (`<t:1789970400:F>` = 11:30 AM IST) per weekly rhythm.
- Mod tickets: Ticket Tool flow — e.g. **#583** `#oth-akulmach74-0583` (Category "Other", opened 20 Sep);
  ping the mod inside the ticket. Ticket UI has an **"Escalate to Nihilus"** button (Nihilus = second
  mod contact path).
- Captain's screenshot timestamps are device-local = **IST** (confirmed 20 Sep: `<t:1789970400:F>`
  rendered "Monday, September 21, 2026 at 11:30 AM").
- **Week 6 (FINAL) confirmed 21 Sep:** Match **Week 6 #630** vs **@charliebrown0002** (Reg SP 23,300,
  3 players, IDs 43790139/8122896/65346371) · map **Imperial Temple** · Bo3 CPC · lobby Equalize.
  Our listed Reg SP on the W6 list = **23,000** (registration value); post-removal 22,700 recorded 20 Sep —
  display discrepancy noted, MM list is the pairing source of truth. List shows only our 3 remaining IDs
  → removals propagated ✅.
- W6 official deadlines: ticket **Fri 25 Sep 6:00 AM UTC** `<t:1790316000:F>` (last of season);
  match + results **Sun 27 Sep 6:00 AM UTC** `<t:1790488800:F>` = season end; reschedule needs ≥6h notice;
  72h silence → ticket; wrong map = match won't count. After W6: results final, A-Coins paid.
- Stefania app creates W6 battle-post threads and tags both leaders (same bot that recorded the W5 result).
- W6 battle-post thread: full scheduling log verbatim in `Week_6_Brief.md` §5 — currently waiting on
  Charlie Brown's counter-times (his 22 Sep 2:44 AM message rejected our slots).
- **Gladiator = team mentor** — Discord `gladiator_22837` · `<@1217130504357413015>` (ID from the
captain's Week 4 team brief; captain confirmed 21 Sep).
- **Wednesday practice = standing weekly rhythm** (captain-stated 21 Sep): W4 team brief scheduled
  practice Wed 16:00 UTC (`<t:1788969600:F>`); W6 = Wed 23 Sep 16:00 UTC (`<t:1790179200:F>`).
  Sat 19 Sep casual practice ran 9:30 PM IST.
- **Captain's team-brief style (Week 4 sample, 21 Sep):** single message — role ping + "Week N **#M**
  vs **@opponent** · **Map** Bo3" header → "already pinged them. **exact available times**" → weekend
  slots with `||UTC: X||` spoilers + "← best" arrow → "asked lock before <stamp>" → "hangars attached
  below" → "practice Wednesday ~1 hour" line → mentor ping with starter-comp ask. Reuse weekly.
- Captain on the W6 SP gap (23,300 vs 23,000): "fine, 300 here and there" (21 Sep) — not a concern.
  **MAQC website profile + W6 MM list both show Reg SP 23,000** (captain check 21 Sep) even after
  night fury set 22,700 on 20 Sep — display discrepancy stands; captain unconcerned.
- **Comms:** captain doesn't usually speak on mic. Comms ask SENT 21 Sep 7:34 PM IST (shortened
  as-sent text in brief §5). **BoWolf 21 Sep 8:02 PM: team OK without comms; he plays on MOBILE so
  voice isn't possible for him.** Gunshot + Gladiator never answered on comms — **RESOLVED 23 Sep
  (captain's call): NO voice comms for W6, in-game text callouts only; unanswered asks moot, item
  closed, don't re-ask.** Captain re-pinged Gunshot
  under the roster update 21 Sep 7:34 PM (nudge, edited).
- **Gladiator's Imperial Temple plan (verbatim 22 Sep 12:30 AM IST, brief §7):** charge-Voidghost
  opener — both weapons charged, fire one, activate ability, take middle beacon, fire other weapon,
  reactive ability back to safety; then keep the charge void alive as long as possible to get mid.
  Captain asked BoWolf 22 Sep 7:05 PM "can you run charge voidghost? practiced them?" — ✅ ANSWERED
  23 Sep: BoWolf noted he doesn't have maxed Charge 12s or 16+8 setup, but agreed to buy/upgrade Charge 12s
  for Voidghost. Gladiator-opener pilot = BoWolf (charge-Voidghost).
- **Wednesday Practice Cancelled (23 Sep):** Practice pinged for 9:30 PM IST / 16:00 UTC (timezone ping
  confusion 2:00 AM / 11:30 AM fixed). Cancelled due to Gunshot being at hospital with family and BoWolf
  on late work shifts/calls. Team agreed to skip practice for the week and head straight into Match #630
  relying on existing synergy and familiarity.
- **Gunshot 21 Sep 7:34 PM (team channel):** "3v3 ?" [✅] / "3v5 ?" [❌] — asking the W6 match format;
  3v3 consistent with night fury's even-pair ruling. **Gunshot is IN for Week 6** (captain-confirmed
  22 Sep). Bowolf's W6 availability: not explicitly confirmed (comms answered only).
- **Captain's Discord display names:** **Eipstenian** (team server, BULB badge) / **Akulmach74**
  (battle posts) — same person; OCR aid for future screenshots.
- **Opponent scout intel (prep reference):** Charlie Brown leader ID 43790139; match Reg SP **23,300** across 3 players (IDs 43790139, 8122896, 65346371). Specific mech/weapon loadout assumptions omitted.
- **Team brief (single, captain's W4 format) SENT 21 Sep** — match header, Sat anchors + weekday
  backups, lock-by stamp, hangars line, Wed practice, Gladiator strat ask. As-sent comp ask (edited):
  **voidghost -> mid, eclipse -> effect support, Outlaw -> crash people coming to mid** (3-mech comp,
  not the drafted 5-mech list); opponent hangar scout screenshots attached (brief §8).
- **Scheduling thread (W6 #630, times IST):** Charlie asked 21 Sep 8:35 AM → captain's v2 availability
  reply SENT 21 Sep 7:17 PM (edited; verbatim in brief §5) → **Charlie 22 Sep 2:44 AM: "All of those
  times are like 11pm for me and 3am for my teammates" — slots rejected** → captain 22 Sep 7:03 PM
  asked his timezone (guess: UTC+8 him / UTC+12 teammates — arithmetically consistent with 11pm/3am
  at 15:00 UTC, but unconfirmed) + 7:12 PM asked for **EXACT** counter-times (both edited).
  **NO LOCK YET** — must lock before Fri 25 Sep 06:00 UTC `<t:1790316000:F>`.
- **Charlie's timezone ANSWERED (23 Sep 5:24 AM IST, screenshot):** *"I'm un alaska and they are new
  York. so eastern and pacific time zone"* + *"I have your comms if your available"* → him **AKDT
  (UTC−8)**, teammates **Eastern (UTC−4) / Pacific (UTC−7)**. This DISPROVES the earlier UTC+8/UTC+12
  guess (which matched his "11pm/3am" complaint numbers). Under Alaska zones, 15:00 UTC = **7:00 AM him
  / 11:00 AM NY / 8:00 AM PT** — a morning, not "11pm/3am" → suspect **device-region mismatch** (Discord
  `<t:>` stamps render per the DEVICE's zone, so wrong device region = wrong displayed time). NOTE: a
  device-region error on Charlie's side would make BOTH of his complaint readings wrong, and it also
  means his "I have your comms if your available" might read oddly. Draft 5 (brief §5, ready 23 Sep,
  **NOT sent**) offers **16:00 UTC Thu/Fri/Sat** (9:30 PM IST / noon EDT / 8 AM AKDT / 9 AM PDT;
  stamps `<t:1790265600:F>` / `<t:1790352000:F>` / `<t:1790438400:F>`), asks him to check his device
  region, and clarifies the comms line (our side = text callouts, BoWolf is mobile-only). Fallback if
  8 AM AK is refused: **17:00 UTC** same days (`<t:1790269200:F>` / `<t:1790355600:F>` /
  `<t:1790442000:F>`). Practice Wed 23 Sep 16:00 UTC `<t:1790179200:F>` unchanged. Same-day note:
  screenshots in that timezone chat show "11pm for me and 3am for teammates" from the thread — recorded
  verbatim in the brief's thread log.

## Technical lessons & edge cases
- Diverged local history after a reset: fetch branch → hash-compare trees → `reset --soft`
  to remote tip → recommit diff → push. Verify FETCH_HEAD tip first; it can flip between calls.
- Re-saved PDFs may differ in bytes but be content-identical — verify by normalized text extraction
  (watch for `·` → `ï¿½` mojibake), and prefer the clean-encoding blob.
- `edit_file` fuzzy match can fail on emoji/special-char anchors — use small unique anchors or grep first.
- **CRITICAL: never batch multiple `edit_file` calls to the SAME file in one block** — parallel
  read-modify-write races silently clobber each other (Sep 15: several "successful" same-file edits
  lost). One edit per file per block; edits to DIFFERENT files may batch. Always grep-verify
  before committing. For multi-file updates, a single asserted python replacement script is safest.
