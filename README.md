# Work Analytics Dashboard

Interactive, client‑side analytics for Azure DevOps work items. Upload a CSV and explore KPIs, trend charts, heatmaps, and aging analysis—no server required.

## Live Dashboard

- Web portal: https://SasidharPV.github.io/WorkAnalyticsDashboard/
- Entry file: `index.html` (redirects to `dashboard.html`)

If the site isn’t live yet, enable GitHub Pages: Settings → Pages → Source = GitHub Actions.

## What’s inside

- KPIs for PBIs (Product Backlog Items) only
- Tickets per person, monthly trends, inflow vs outflow
- Aging scatter (state vs age), age histogram, age by state
- Developer monthly heatmap with in‑cell counts and tooltips
- Quarterly PBI analysis and Feature analytics (created per quarter) with table

## How to use

1) Open the web portal (or double‑click `index.html` locally).
2) Click “Choose File” and select your CSV export.
3) Explore charts; optional “Download Report as PDF”.

All processing happens in the browser—data is not uploaded anywhere.

## CSV format (columns expected)

- Core: `Work Item Id`, `Work Item Type`, `Title`, `State`, `Assigned To`
- Dates (MM/DD/YYYY preferred): `Created Date`, `Start Date`, `Closed Date`, `State Change Date`
- Blocking: `DEBLOCKED` (TRUE/FALSE; only TRUE is considered blocked)

Notes:
- PBIs-only metrics/charts are filtered to `Work Item Type = Product Backlog Item`.
- Feature analytics use `Work Item Type = Feature`.

## Tech stack

- Charting: Chart.js 3.9
- CSV parsing: PapaParse
- UI: Bootstrap 5
- PDF export: html2pdf.js

## Local development

- Main file: `dashboard.html`
- Open in a browser (no server needed). For CSV file access, Chrome may require running with local file access enabled; Edge/Firefox usually work out of the box.

## Deployment

- GitHub Pages via Actions workflow: `.github/workflows/deploy-pages.yml`
- Site root includes `index.html` → `dashboard.html`

## Troubleshooting

- Tooltips or colors missing: hard refresh (Ctrl+F5) to clear cache.
- Empty charts: verify CSV has the expected columns and date format.
- Pages not live: check Actions tab for the Pages workflow run and Settings → Pages configuration.

---

PRs/issues welcome.