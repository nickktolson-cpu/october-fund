# October Fund — Weekly Update Guide

When you update your stats, you only need to edit `index.html`. Here's every value and its line number.

---

## HEADLINE STATS (Lines 706–726)

These are the animated stat cards. Change the `data-count` value:

| Stat         | Line | What to change                          | Example          |
|-------------|------|-----------------------------------------|------------------|
| Total Trades | 706  | `data-count="190"`                      | → `data-count="210"` |
| Win Rate     | 710  | `data-count="89.5"`                     | → `data-count="90.2"` |
| Profit Factor| 714  | `data-count="2.18"`                     | → `data-count="2.25"` |
| Expectancy   | 718  | `data-count="244"`                      | → `data-count="260"` |
| Gross P&L    | 722  | `data-count="46275"`                    | → `data-count="52000"` |
| Return %     | 726  | `data-count="231"`                      | → `data-count="260"` |

**How to calculate Return %:**  Total Gross P&L ÷ $20,000 × 100

---

## EQUITY CURVE HEADER (Line 737)

Update the displayed return to match:
```
<div class="curve-return">+231%</div>
```
Change `+231%` to match your new Return %.

---

## EQUITY CURVE DATA (Lines 974–982)

These control the shape of the equity curve chart:

| Variable       | Line | What it is                         | How to update                |
|---------------|------|------------------------------------|------------------------------|
| `endEquity`    | 975  | $20,000 + total gross P&L         | Change to `20000 + new P&L`  |
| `totalTrades`  | 977  | Total trade count                  | Match your Total Trades stat |
| `phase1Trades` | 981  | Trades in TradingView phase        | **Keep at 100** (don't change) |

**Leave `startEquity` (20000) and `phase1End` (50000) alone** — those are historical.

`phase2Trades` auto-calculates from `totalTrades - phase1Trades`.

---

## INSTRUMENT TABLE (Lines 766–793)

Each instrument row has 3 values to update — trades count, win rate bar width + text, and P&L:

### MNQ (Lines 766–769)
```html
<td>131</td>                              ← trade count
... style="width:93%" ... 93%             ← win rate (update BOTH the width % and text)
<td class="pnl-positive">+$39,883</td>   ← net P&L
```

### MCL (Lines 772–775)
Same pattern. Update trade count, width % + text, and P&L.

### NQ (Lines 778–781)
Same pattern.

### MGC (Lines 784–787)
Same pattern.

### CL (Lines 790–793)
Same pattern. Note: if P&L is negative, use `class="pnl-negative"`.

**To add a new instrument:** Copy any `<tr>...</tr>` block and paste it before the closing `</tbody>`. Update the values.

---

## SIGNAL / CURRENT EVENTS (Lines 808–812)

```html
<div class="event-date">April 4, 2026</div>
<div class="event-headline">Your Headline Here</div>
<div class="event-body">
  Your commentary here.
</div>
```

Update the date, headline, and body text whenever you want.

---

## WEEKLY UPDATE CHECKLIST

1. Open `index.html` on GitHub (click the file → pencil icon to edit)
2. Update the 6 headline stats (lines 706–726)
3. Update curve return display (line 737)
4. Update `endEquity` and `totalTrades` (lines 975, 977)
5. Update instrument table rows (lines 766–793)
6. Update the Signal section if desired (lines 808–812)
7. Click "Commit changes" — site updates in ~60 seconds

Total time: ~2 minutes once you know the flow.
