# AKIJ Resource — Revenue Assurance & Marketing Forecast

Interactive dashboard for the FY 2026-27 revenue-assurance analysis of AKIJ Resource Ltd,
produced by the Strategic Planning & Analysis function.

- **What it shows** — per-SBU marketing situation (revenue vs plan, Marketing Revenue/Profit,
  spend, gaps) and a 9-month forecast (Oct-26 → Jun-27) projecting where each SBU lands if the
  current trend holds.
- **Data** — DWH `fin.tblAccountingJournalArc` (GL 3010001 + 3010002 revenue, 4210001 marketing,
  4810001 COGS), as-of 9 Sep 2026. Units: BDT Crore.
- **Forecast method** — seasonal × trend (prior-year month × (1 + Q1-to-date YoY growth)).

Live: https://abirulislam-ops.github.io/akij-resources-revenue-assurance/

## Regenerate

```powershell
python dwh_extract.py        # refresh DWH extract -> rap_extract.json
python add_sep_mtd.py        # like-for-like Sep-25 MTD
python build_web.py          # rebuild web/index.html
```

Then commit and push `web/index.html` to `main`.
