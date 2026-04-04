# October Fund — Weekly Update Guide
 
Edit `index.html` on GitHub (click file → pencil icon → commit). Site updates in ~60 seconds.
 
---
 
## HEADLINE STATS (Lines 166–171)
 
Change the `data-count` value in each line:
 
| Stat         | Line | What to change                          |
|-------------|------|-----------------------------------------|
| Total Trades | 166  | `data-count="190"`                      |
| Win Rate     | 167  | `data-count="89.5"`                     |
| Profit Factor| 168  | `data-count="2.18"`                     |
| Expectancy   | 169  | `data-count="244"`                      |
| Gross P&L    | 170  | `data-count="46275"`                    |
| Return %     | 171  | `data-count="231"`                      |
 
**Return % formula:** Total Gross P&L ÷ $20,000 × 100
 
---
 
## EQUITY CURVE HEADER (Line 178)
 
```html
<div class="curve-return">+231%</div>
```
Change `+231%` to match your Return %.
 
---
 
## EQUITY CURVE DATA (Lines 362–368)
 
| Variable       | Line | What it is                         | How to update                |
|---------------|------|------------------------------------|------------------------------|
| `endEquity`    | 363  | $20,000 + total gross P&L         | Change to `20000 + new P&L`  |
| `totalTrades`  | 365  | Total trade count                  | Match your Total Trades stat |
| `phase1Trades` | 366  | Trades in TradingView phase        | **Keep at 100** (don't change) |
| `endDate`      | 368  | Last trade date                    | e.g. `new Date('2026-04-09')` |
 
**Leave `startEquity` (20000) and `phase1End` (50000) alone** — those are historical.
 
---
 
## MONTHLY BREAKDOWN (Lines 193–249)
 
Each month card has 4 editable values:
 
```html
<div class="month-name">December 2025</div>          ← month label
<div class="month-pnl pnl-positive">+$8,200</div>    ← monthly P&L
...
<div class="month-stat">Trades: <span>35</span></div> ← trade count
<div class="month-stat">WR: <span>91%</span></div>    ← win rate
...
<div class="month-context">Your blurb here.</div>     ← macro commentary
```
 
**Monthly P&L values should sum to your total Gross P&L.**
 
Current months: Dec (line 196), Jan (line 207), Feb (line 218), Mar (line 229), Apr (line 240).
 
**To add a new month:** Copy any `<div class="month-card">...</div>` block and paste it before the closing `</div>` of the monthly-grid. Update all values.
 
---
 
## INSTRUMENT TABLE (Lines 256–261)
 
Each row: trade count, win rate bar `width:XX%` + text, and P&L.
 
```html
<td>131</td>                              ← trade count
... style="width:93%" ... 93%             ← win rate (update BOTH)
<td class="pnl-positive">+$39,883</td>   ← net P&L
```
 
For negative P&L, use `class="pnl-negative"` and red bar: `background:var(--red)`.
 
---
 
## SIGNAL / CURRENT EVENTS (Lines 270–272)
 
```html
<div class="event-date">April 4, 2026</div>
<div class="event-headline">Your Headline</div>
<div class="event-body">Your commentary.</div>
```
 
---
 
## WEEKLY CHECKLIST
 
1. Open `index.html` on GitHub → pencil icon to edit
2. Update 6 headline stats (lines 166–171)
3. Update curve return display (line 178)
4. Update `endEquity`, `totalTrades`, `endDate` (lines 363, 365, 368)
5. Update current month card in monthly breakdown (lines 193–249)
6. Update instrument table (lines 256–261)
7. Update Signal section if desired (lines 270–272)
8. Click **Commit changes** — live in ~60 seconds
 
