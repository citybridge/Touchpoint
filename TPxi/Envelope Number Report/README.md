# Envelope Number Report

A SQL report that generates a complete mailing list of all envelope holders with their envelope number, properly formatted name, and full mailing address. Handles joint envelopes, individual envelopes, and deceased spouse scenarios — ready for export to your envelope printing vendor.

With this report, you can:

- Pull all active envelope holders with their assigned envelope number
- Format joint names automatically (e.g. "Mr. and Mrs. John Smith")
- Handle deceased spouse cases (falls back to individual name)
- Include individual envelope holders separately
- Flag children under 18 who have envelope options set
- Exclude deceased, archived, no-address, and do-not-mail records
- Export results for envelope printing or mail merge

---

## How It Works

The report uses CTEs to handle four distinct scenarios, then combines them with `UNION ALL`:

| CTE | Scenario |
|-----|----------|
| `EnvJoint` | Both spouses alive, joint envelope (EnvelopeOptionsId = 2) |
| `EnvJointDeceased` | Joint envelope but one spouse is deceased or no spouse |
| `EnvIndividual` | Individual envelope (EnvelopeOptionsId = 1) |
| `EnvChild` | Children under 18 with envelope options set |

### Envelope Number Format

Envelope numbers are stored in `PeopleExtra` as the field `EnvelopeNumber`. The output format is:

- **Has envelope number**: `EnvelopeNumber-PeopleId` (e.g. `142-3456`)
- **No envelope number**: `PeopleId` only (e.g. `3456`)

---

## Output Columns

| Column | Description |
|--------|-------------|
| Name | Formatted name (joint, individual, or child) |
| PrimaryAddress | Street address line 1 |
| PrimaryAddress2 | Street address line 2 |
| PrimaryCity | City |
| PrimaryState | State |
| PrimaryZip | ZIP code |
| EnvelopeNumber | Formatted envelope number with PeopleId |
| EnvelopeChoice | Envelope option description (Joint/Individual) |
| FamilyPosition | Position in family (Head, Spouse, Child) |

---

## Assumptions

- Envelope numbers are stored as an Extra Value (`PeopleExtra`) with `Field = 'EnvelopeNumber'` and `IntValue`
- `EnvelopeOptionsId`: 1 = Individual, 2 = Joint
- Only head of household records are included for joint envelopes
- Excludes deceased, archived, empty-address, and do-not-mail people

---

## Setup

1. Navigate to **Admin > Advanced > Special Content > SQL Scripts**
2. Click **New SQL Script File**, name it `Envelope Number Report`
3. Paste the contents of `EnvelopeNumber.sql`
4. Add to CustomReports XML:
   ```xml
   <Report name="Envelope Number Report" type="SqlReport" role="Finance" />
   ```

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
