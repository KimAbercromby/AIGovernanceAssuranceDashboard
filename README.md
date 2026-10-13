# AI Assurance Dashboard

A quarterly AI assurance dashboard for a local authority. It answers one question for an Information Governance Board: **is AI governance working?**

It brings together the five kinds of assurance data:

| Domain | What it shows |
| --- | --- |
| Register | Systems with an owner and risk tier, reviews on time |
| Control | DPIAs signed off before go-live, approval time |
| Performance | Staff edit rate on AI outputs, by team, against a tolerance |
| Incident | Accuracy complaints, near misses, breaches, shadow AI finds |
| Supplier | Suppliers with current assurance evidence |

…and turns findings into owned, dated actions for the Board.

## What it does

- **Scorecard**: each measure against its target, with the change since the previous period. Only a missed target is flagged.
- **Performance drift**: edit rates by team, with the team furthest over tolerance highlighted.
- **Early warnings**: incident trends, read the right way (rising near misses and shadow AI finds can be healthy; breaches should fall).
- **AI register**: review status is worked out from the review due date (Overdue once passed, Due soon within 60 days). Search, filter, sort and download.
- **Consistency check**: compares the scorecard against the register and warns when they disagree, so a stale return isn't reported to the Board.
- **Action log**: open actions past their due date are flagged as Late.
- **Print Board report**: a print-friendly layout.

## Using your own data

Select **Load your data**, download the CSV templates, fill them in (Excel or Google Sheets, saved as CSV) and load them back. Dates can be `YYYY-MM-DD` or UK `DD/MM/YYYY`.

Files are read in your browser only. Nothing is uploaded or sent anywhere. Loaded data is remembered in that browser until you select **Reset to sample data**.

| File | Columns |
| --- | --- |
| `assurance_kpis.csv` | id, domain, kpi, value, previous, target, unit, better (higher/lower), definition |
| `ai_register.csv` | system, service, risk_tier, owner, next_review, dpia, supplier_evidence |
| `edit_rates.csv` | period, team, edit_rate |
| `incidents.csv` | period, complaints_accuracy, near_misses, breaches, shadow_ai_found |
| `actions.csv` | ref, action, finding, owner, due, status |

## Sample data

The built-in data is illustrative, for a fictional local authority. It is not real council data.

## Running it

It is one self-contained `index.html` with no dependencies. Open it in a browser, or host it with GitHub Pages (Settings → Pages → Deploy from branch → `main`, root).
