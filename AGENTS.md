# AGENTS.md

## Project Rules

This project is currently a Phase 1.2 localStorage MVP.

Do:
- Keep the app working as a static browser app.
- Preserve HTML + CSS + jQuery + Chart.js.
- Preserve localStorage save/load behavior.
- Preserve JSON backup/restore compatibility.
- Preserve CSV export.
- Preserve Salary Outgoing tracking.
- Preserve the clean black-and-white finance/admin UI.
- Add comments around important data model logic.
- Make small, safe, testable changes.

Do not:
- Do not add Supabase yet.
- Do not add a backend yet.
- Do not add React yet.
- Do not add a build system yet.
- Do not remove existing features.
- Do not rename data fields without migration support.
- Do not break old localStorage data.

## Testing Expectations

After changes, manually test:
- Dashboard render
- Month/year filters
- Employee add/edit/archive/restore
- Salary history add/edit
- Salary Outgoing generate/edit/paid/pending/cancel/archive
- Client add/edit/archive/restore
- Payment add/edit/paid/pending/overdue/cancel/archive
- Reports
- CSV export
- JSON backup/restore
- Local PIN lock

## Coding Style

- Keep code readable.
- Prefer small helper functions.
- Avoid overengineering.
- Add comments where the localStorage schema is defined.
- Use clear function names.
- Keep all user-facing currency in Philippine Peso.
