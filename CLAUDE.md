# FPL 2026/27 — Yemi

Season-long Fantasy Premier League file. Read this before any weekly advice.

## Target

**Top 5,000 overall.** ~0.05% of ~11M entries. Not promisable — process aims to make it
plausible, not certain. Realistic skill floor with disciplined play is top 50–100K; 5K
needs a differential or two to land.

## Hard user rules

- **Bruno Fernandes (MUN, £12.0m) must always be in the squad.**
- **Erling Haaland (MCI, £15.5m) must always be in the squad.**
- Never sell either without explicit permission, even when the numbers say otherwise.

## Data source — always use this, never memory

```bash
curl -s https://fantasy.premierleague.com/api/bootstrap-static/   # prices, ownership, status, news
curl -s 'https://fantasy.premierleague.com/api/fixtures/?future=1' # fixtures + FDR
curl -s https://fantasy.premierleague.com/api/element-summary/<player_id>/  # per-player history
curl -s https://fantasy.premierleague.com/api/entry/<TEAM_ID>/event/<GW>/picks/  # my picks (needs TEAM_ID)
```

`status`: `a` available · `d` doubtful (see `chance_of_playing_next_round`) · `i` injured ·
`s` suspended · `u` unavailable. `news` field carries the reason.

**TEAM_ID = 4091146** (Yemi Oloko, Nigeria, entry joined 12 Aug 2026, `started_event: 1`).
Verified live. Favourite team on the account is Arsenal — irrelevant to selection, noted only
so the zero-Arsenal squad is not mistaken for an oversight.

```bash
curl -s https://fantasy.premierleague.com/api/entry/4091146/                    # rank, points, chips
curl -s https://fantasy.premierleague.com/api/entry/4091146/event/<GW>/picks/   # actual XI + captain
curl -s https://fantasy.premierleague.com/api/entry/4091146/history/            # season + past history
curl -s https://fantasy.premierleague.com/api/entry/4091146/transfers/          # transfers made
```

**Always read the real picks from the API before advising. Never trust this file's squad
table alone** — it drifts the moment a transfer is made outside a session.

## Season facts (2026/27)

- GW1 deadline **Fri 21 Aug 2026, 18:30 BST** (17:30 UTC). Deadlines run weekly, Fri 17:30 UTC.
- **8 chips, two sets.** Set 1 (WC/FH/BB/TC) expires at the **GW19 deadline, Sat 2 Jan 2027**.
  Set 2 runs GW20–38. Unused first-half chips are lost, not carried.
- Wildcard 1 and Free Hit 1 usable GW2–19. Bench Boost and Triple Captain usable GW1–19.
- **No Assistant Manager chip** — confirmed absent from the API chip list.
- Defensive Contribution unchanged: DEF 10 CBIT, MID/FWD 12 CBIRT, capped +2/match.
- BPS tweaked: 1 BPS per **three** clearances/blocks/interceptions (was two) — reduces
  DefCon/bonus double-dipping, slightly devalues pure defensive CBs for bonus.
- Only two players above £9.5m: Haaland £15.5m, Bruno £12.0m. Both are locked here, so
  **£27.5m of £100m is spent before any decision is made.** Every other slot must earn its
  place on points-per-million.

## Notable summer moves baked into prices

Semenyo → MCI · Guéhi → MCI · Rogers → CHE · Isak → LIV · João Pedro CHE main striker ·
Calvert-Lewin → LEE · Brobbey → SUN · Bruno Guimarães → ARS · Wissa + Woltemade → NEW ·
Dubravka, Senesi, Van Hecke → TOT. Promoted: **Coventry, Hull, Ipswich**.

## GW1 squad (£100.0m exactly, £0.0 bank)

| Pos | Player | Club | £ | Own% |
|---|---|---|---|---|
| GK | Verbruggen | BHA | 4.5 | 17.9 |
| GK | Dovin *(bench)* | COV | 4.0 | 2.4 |
| DEF | Shaw | MUN | 4.5 | 24.2 |
| DEF | O'Reilly | MCI | 6.5 | 22.3 |
| DEF | N. Williams | NFO | 5.0 | 12.0 |
| DEF | van Ewijk *(bench)* | COV | 4.0 | 15.5 |
| DEF | Diop *(bench)* | IPS | 4.0 | 18.6 |
| MID | **B. Fernandes** | MUN | 12.0 | 48.2 |
| MID | Szoboszlai | LIV | 7.0 | 43.8 |
| MID | Semenyo | MCI | 8.5 | 26.5 |
| MID | Mbeumo | MUN | 8.0 | 24.4 |
| MID | Hughes | CRY | 4.5 | 11.1 |
| FWD | **Haaland** | MCI | 15.5 | 73.6 |
| FWD | João Pedro | CHE | 7.5 | 55.8 |
| FWD | Kusi-Asare *(bench)* | FUL | 4.5 | 7.5 |

**XI (3-5-2):** Verbruggen; Shaw, O'Reilly, N. Williams; Bruno, Szoboszlai, Semenyo,
Mbeumo, Hughes; Haaland, João Pedro.
**Bench order:** 1 Diop · 2 Kusi-Asare · 3 van Ewijk · GK Dovin.
Ordered by GW1 fixture, not by price: IPS home to SUN (2), FUL home to CHE (4), COV away at
ARS (5). Re-order this every week — it is the cheapest fixture-first decision in the game.
**Captain: Haaland.** Vice: Bruno.

### Why this shape

- Fixture engine GW1–8 (mean FDR): LIV 2.75, CRY/MUN/NEW/SUN 2.88, ARS/CHE/MCI/TOT 3.00.
  BOU worst at 3.50 — avoid Bournemouth assets early.
- MUN opens HUL(H), ips(a), EVE(H) — best three-week run in the game, and Bruno is forced
  anyway, so Shaw and Mbeumo ride the same fixtures cheaply.
- Szoboszlai is the single best value in the game right now: £7.0m, LIV's best fixture run,
  penalty order 2, and DefCon-eligible from midfield.
- Bench is deliberately £12.5m of pure fodder. With £27.5m locked in two players, a real
  bench is unaffordable — accept the 4-man bench being non-scoring and never Bench Boost
  before a wildcard rebuild.

### Known constraints in this squad

- **MUN and MCI are both at the 3-player cap.** Cannot add Cherki, Doku, Cunha or any other
  City/United asset without selling one first. Flag this before recommending any such move.
- £0.0 in the bank. First transfer is free, so this costs nothing at GW1, but it removes
  price-rise flexibility from GW2.

## Chip plan (first half)

| Chip | Target | Trigger to revisit |
|---|---|---|
| Wildcard 1 | **GW8–10** | Pull earlier if 3+ starters are injured or benched |
| Triple Captain | Haaland home vs a promoted side, post-wildcard | Needs a confirmed single-GW fixture |
| Bench Boost | Only after WC1 has built a real bench | Never on this GW1 bench |
| Free Hit | Hold for the first blank/heavy-rotation week | — |

All four expire **2 Jan 2027**. Track this.

## Automated weekly agent

**Routine `trig_019i3wag6sFoqcvcAdWaRnmF`** — cron `0 8 * * 4`, every Thursday 08:00 UTC
(09:00 WAT), model Opus 5. Manage at https://claude.ai/code/routines/trig_019i3wag6sFoqcvcAdWaRnmF
(Claude Code cannot delete routines; disable or delete via that page.)

It pulls live bootstrap/fixtures/entry data, runs the routine below, and leaves a **Gmail
draft** to yemi.oloko@gmail.com — the Gmail connector can create drafts but not send, so the
draft must be opened manually. Full output also lives at the routine's session link.

**It runs in Anthropic's cloud and cannot read this directory.** The strategy is therefore
duplicated verbatim inside the routine prompt. **Any change to the rules below must be
mirrored into the routine** via `RemoteTrigger` `action: "update"`, or the weekly call will
silently follow the old strategy. This is the main maintenance cost of the setup.

It also cannot write `season-log.md`. It emits a ready-to-paste log entry instead; paste it
in, or ask in a session and it gets appended from the live API.

## Weekly routine (run every Thursday or Friday before 17:30 UTC)

1. Re-pull `bootstrap-static` — do not reason from stale prices or last week's ownership.
2. Check `status` and `news` on all 15. Any `d`/`i`/`s` gets resolved first.
3. Pull fixtures; recompute the 3-GW and 6-GW difficulty sums per club (see Fixture-first §5).
4. Rank candidates by **3-GW expected points**, opponent-adjusted — never by past points alone.
   Before GW8 that means targeting Coventry/Hull/Ipswich fixtures; after ~GW10 it means the
   measured bottom of the table by `expected_goals_conceded_per_90`.
5. Decide transfer: **a −4 hit needs ~+4 expected points over the 3-GW horizon, not over one
   GW.** Default is roll and bank — up to the 5-transfer cap.
6. Captain: highest expected points *this* GW, opponent-weighted, then adjusted by rank state.
   Captaincy is the one call that is correctly single-week — it carries no future cost.
7. Log the decision in `season-log.md`, including the 3-GW numbers the call was based on.

## Fixture-first selection — the governing rule

**Never pick on a player's past points alone. Points are the evidence; the fixture is the
forecast.** A 12-point haul against Hull tells you far less than the same haul at Anfield.
Always price the opponent in before the name.

### 1. Early season — target the promoted three

Until roughly GW8 there is no reliable table, so **the promoted sides are the only defensive
weakness you can identify with confidence**: **Coventry, Hull, Ipswich**. Prioritise attackers
whose next fixtures include them, and treat their own defenders as clean-sheet traps
regardless of price (this squad holds Dovin, van Ewijk and Diop strictly as non-playing
bench fodder, never as points sources).

### 2. From ~GW10 — switch the input from promoted to actual table

Once ~10 rounds are played, the table and underlying numbers stabilise. Replace "promoted"
with **measured defensive weakness**, ranked by:

1. **Expected goals conceded per 90** (`expected_goals_conceded_per_90` in bootstrap) — the
   most predictive single field, better than league position or goals conceded.
2. Bottom-six league position — noisier, but the market prices off it, so it drives price
   rises too.
3. Home/away split. Attacking assets at home against a bad away side is the strongest cell.

Target attackers facing that list. Target defenders and keepers of strong teams *playing*
that list.

### 3. Always evaluate over a 3-gameweek window, never one week

One free transfer per week means a player bought for a single fixture is still in the squad
for the two after it. So:

- Score every candidate as **summed expected points across the next 3 GWs**, not the next one.
- A player with one great fixture followed by two hard ones usually loses to a player with
  three medium ones. Reject the one-week spike.
- Before any transfer, check the incoming player's **GW+1 and GW+2** as well. If either is a
  4 or 5 FDR, the move needs to be clearly better on the 3-week sum to survive.
- Corollary: **sell decisions use the same window.** Do not sell a good asset because of one
  hard fixture inside an otherwise strong run.

### 4. But the 1-transfer constraint is looser than it looks

`game_settings` confirms `max_extra_free_transfers = 4` — **free transfers bank up to 5**
(1 base + 4 saved), and `transfers_cap = 20` is the per-GW ceiling. That changes the plan:

- Rolling to 2 free transfers is the **default**, not a fallback. It converts the 3-week
  horizon from a cage into a planning window.
- Banking 3–5 lets you execute a **fixture-swing in one hit** — pivot several assets onto a
  good run at the moment it starts, without a points hit and without burning a wildcard.
- Ceiling is 5. Banking past 5 wastes transfers, so spend down before hitting the cap.
- This does **not** license weekly cherry-picking. Each transfer still costs a future
  transfer; the 3-GW scoring rule above still decides whether one is worth spending.

### 5. Fixture ticker — recompute every week, do not reuse

```bash
curl -s 'https://fantasy.premierleague.com/api/fixtures/?future=1'
```
Sum `team_h_difficulty` / `team_a_difficulty` per club over the next 3 and next 6 GWs. The
3-week number drives this week's transfer; the 6-week number drives wildcard timing. FDR is
set by FPL and lags reality — override it with `expected_goals_conceded_per_90` when the two
disagree, and say so in the log.

## Rank-state strategy — the part most people get backwards

- **Rank better than target** (inside ~5K): protect. Own the template, captain the crowd,
  take fewer differentials. Variance is now the enemy.
- **Rank worse than target**: take risk deliberately — low-owned captain, off-template
  midfielder. Matching the template while behind guarantees finishing behind.
- Effective ownership matters more than raw ownership for captaincy. Not captaining a 70%+
  owned Haaland in a good fixture is itself a large punt.

## Files

- `season-log.md` — one entry per GW: squad, transfers, captain, points, rank, reasoning.
- Update this file whenever the locked rules, chip state, or squad shape changes.
