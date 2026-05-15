# CODEX_TASKS.md

## Immediate Priorities

1. Run a syntax check on index.html JavaScript.
2. Fix any JavaScript syntax errors.
3. Verify all event handlers exist and work.
4. Verify no console errors appear on page load.
5. Verify Dashboard loads sample data.
6. Verify Salary Outgoing section works.
7. Verify “Generate From Employees” creates payroll rows.
8. Verify Dashboard uses Salary Outgoing for net balance when available.
9. Verify Reports include salary outgoing values.
10. Verify localStorage save/load.
11. Verify JSON backup and restore.
12. Verify CSV exports.
13. Verify local PIN lock.
14. Verify archive/restore/delete actions.
15. Verify payment and payroll status buttons clear payment dates unless status is Paid.

## Specific Code Fixes To Check

- Rename STORAGE_KEY from salaryClientDashboardPhase11 to salaryClientDashboardPhase12, while still migrating old keys safely.
- Keep LEGACY_STORAGE_KEY support for older Phase 1 data.
- Add APP_VERSION = "1.2.0".
- Make sure salaryOutgoings exists when restoring older backups.
- Make sure JSON backup includes salaryOutgoings.
- Make sure Settings backup description mentions salary outgoing/payroll runs.
- Make sure no duplicate IDs are generated.
- Make sure all month/year filters update the visible table/cards.
- Add missing clear-filter buttons if safe.

## Do Not Build Yet

Do not build:
- Supabase integration
- Backend API
- User accounts
- Real authentication
- Recurring payment automation
- Email notifications
- PDF reports
- React conversion

Those are Phase 2 or later.
