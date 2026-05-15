# DATA_MODEL.md

The app stores one JSON object in browser localStorage. Current Phase 1.2 storage key: `salaryClientDashboardPhase12`.

Older supported keys:
- `salaryClientDashboardPhase11`
- `salaryClientDashboardPhase1`

## settings

- `companyName`
- `defaultCurrency`
- `defaultFrequency`
- `salaryReleaseDays` (currently `[5, 20]`)
- `salaryReminderDays`
- `paymentReminderDays`
- `adminEmail`
- `pinCode`

## employees

- `id`
- `name`
- `position`
- `department`
- `startDate`
- `monthlySalary`
- `status`
- `lastIncrease`
- `nextReview`
- `notes`
- `archived`

## salaryHistory

- `id`
- `employeeId`
- `employeeName`
- `previousSalary`
- `newSalary`
- `effectiveDate`
- `reason`
- `notes`

## salaryOutgoings

- `id`
- `employeeId`
- `employeeName`
- `amount`
- `periodStart`
- `periodEnd`
- `scheduledDate` (salary release date; new generated payroll uses the 5th and 20th)
- `paymentDate`
- `status`
- `method`
- `reference`
- `notes`
- `archived`

## clients

- `id`
- `name`
- `contact`
- `email`
- `phone`
- `defaultAmount`
- `frequency`
- `method`
- `status`
- `notes`
- `archived`

## payments

- `id`
- `clientId`
- `clientName`
- `amount`
- `dueDate`
- `paymentDate`
- `status`
- `frequency`
- `invoiceReference`
- `notes`
- `archived`

## activityLogs

- `id`
- `date`
- `action`
- `detail`

## Calculations

- Yearly salary = `monthlySalary * 12`
- Salary increase amount = `newSalary - previousSalary`
- Salary increase percentage = `((newSalary - previousSalary) / previousSalary) * 100`
- Planned monthly payroll = sum of active/probation employee monthly salaries
- Tracked salary outgoing = sum of salaryOutgoings for selected month where status is paid/scheduled/pending, using `paymentDate || scheduledDate || periodStart` as the cash-flow date
- Paid salary outgoing = sum of salaryOutgoings where status is paid
- Expected client income = paid + pending + overdue client payments for selected month
- Net balance = expected client income - tracked salary outgoing, or expected client income - planned payroll if no salary outgoing exists
