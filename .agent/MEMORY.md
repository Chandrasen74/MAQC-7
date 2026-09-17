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
