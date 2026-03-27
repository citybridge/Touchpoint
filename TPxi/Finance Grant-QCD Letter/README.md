# QCD / Grant Letters

A finance tool for generating IRS-compliant Qualified Charitable Distribution (QCD) letters and Grant/Donor Advised Fund acknowledgment letters directly from TouchPoint. Select a date range and the script automatically identifies contributions by batch type, generates individualized letters formatted for windowed envelopes, and optionally saves each letter as a secured note on the person's record.

With this tool, you can:

- Generate QCD letters with required IRS legal language (Section 408(d)(8))
- Generate Grant/Donor Advised Fund acknowledgment letters
- Auto-detect letter type based on TouchPoint batch type
- Print letters formatted for standard windowed envelopes
- Customize letter body, signature image, and sender info via config
- Optionally write each letter as a role-secured note on the person's record
- Use variable placeholders for name, date, amount, fund, and year

---

## Report Selection

Choose a date range to pull all QCD and Grant contributions. The script queries by batch type to automatically separate the two letter types. Optionally enable writing letters as notes on each person's record.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Finance%20Grant-QCD%20Letter/QCDGrantScreenShot.png" width="700" alt="QCD Grant Letters - Report Selection">
</p>

---

## QCD Letter

IRS-compliant Qualified Charitable Distribution letter acknowledging the gift was received directly from the plan trustee. Includes required language about public charity status, no goods/services exchanged, and the distinction between QCD and tax-deductible gifts.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Finance%20Grant-QCD%20Letter/QCDLetteer.png" width="500" alt="QCD Letter Example">
</p>

---

## Grant Letter

Acknowledgment letter for contributions received through donor-advised funds. A simpler format thanking the donor and confirming the gift amount, date, and originating fund.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Finance%20Grant-QCD%20Letter/GrantLetter.png" width="500" alt="Grant Letter Example">
</p>

---

## Configuration

All customization is done in the config section at the top of the script — no code changes needed below the config line.

| Setting | Description |
|---------|-------------|
| `GrantBatchTypeId` | Batch type ID for Grant contributions (Admin > Lookup Codes) |
| `QCDBatchTypeId` | Batch type ID for QCD contributions |
| `Signature` | URL to a signature image overlaid on the letter |
| `ownerId` | PeopleId for the note author (defaults to current user) |
| `roleId` | Role ID that can view the secured note |
| `keywordIdList` | Keyword ID(s) attached to the note |
| `GrantLetterBody` | HTML template for Grant letters |
| `QCDLetterBody` | HTML template for QCD letters |

### Letter Template Variables

Use these placeholders in your letter body templates:

| Variable | Value |
|----------|-------|
| `{0}` | First Name |
| `{1}` | Last Name |
| `{2}` | Full Name |
| `{3}` | Contribution Date |
| `{4}` | Contribution Amount |
| `{5}` | Contribution Description (e.g. grant fund name) |
| `{6}` | Year of contribution |
| `{7}` | Signature image tag |

---

## Assumptions

1. You have separate batch types for Grants and QCDs in TouchPoint
2. Letters are formatted for standard windowed envelopes
3. The note feature uses role-based security to restrict visibility

---

## Printing Tips

| Environment | Notes |
|-------------|-------|
| Mac + Edge + Ricoh | No changes needed |
| Windows + Edge + Ricoh | Use print dialog to remove blank pages; set margins to "None" or "Borderless" |
| General | The last page contains the report menu and generally does not need to be printed |

---

## Setup

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**, name it `Finance_QCDGrantLetters`
3. Paste the contents of `QCD-GrantLetters`
4. Update the config section at the top with your batch type IDs, signature URL, and letter templates
5. Add to CustomReports XML:
   ```xml
   <Report name="Finance_QCDGrantLetters" type="PyScript" role="Finance" />
   ```

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
