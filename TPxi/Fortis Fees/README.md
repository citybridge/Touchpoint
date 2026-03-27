# Fortis Fees

A finance tool for calculating payment processing fees (ACH, Credit Card, American Express) from TouchPoint transaction data. Generates a professional report showing per-program fee breakdowns for backcharging ministry budgets, with CSV export for external analysis.

With this tool, you can:

- Calculate processing fees across ACH, Credit Card, and American Express transactions
- Break down fees by ministry program for accurate backcharging
- Filter by date range with flexible date logic
- View a professional HTML report with per-transaction detail
- Export to CSV for spreadsheet analysis or journal entries
- Configure fee rates and per-transaction costs per payment type

---

## Fee Report

Select a date range to calculate processing fees across all payment types. The report shows transaction counts, total amounts, and calculated fees broken down by ministry program — ready for journal entry backcharges.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Fortis%20Fees/FortisFees.png" width="700" alt="Fortis Fees Report">
</p>

---

## Configuration

All fee rates are configured in the `FortisConfig` class at the top of the script. Adjust these to match your payment processor's fee structure.

| Setting | Default | Description |
|---------|---------|-------------|
| `ach_percent` | 5% | ACH processing fee percentage |
| `ach_per_transaction` | $0.50 | ACH per-transaction fee |
| `cc_percent` | 5% | Credit card processing fee percentage |
| `cc_per_transaction` | $0.50 | Credit card per-transaction fee |
| `amex_percent` | 5% | American Express processing fee percentage |
| `amex_per_transaction` | $0.50 | American Express per-transaction fee |

### Payment Type Codes

| Code | Type |
|------|------|
| `B` | ACH / Bank transfer |
| `C` | Credit Card (including Amex) |

---

## How It Works

1. User selects a date range and submits the form
2. Script queries TouchPoint's `Transaction` table filtered by date and payment type
3. Fees are calculated per transaction using the configured rates
4. Results are grouped by ministry program for backcharge allocation
5. Output is rendered as an HTML report or downloaded as CSV

---

## Setup

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**, name it `Finance_FortisFees`
3. Paste the contents of `TPxi_FortisFees.py`
4. Update the `FortisConfig` class with your fee rates
5. Add to CustomReports XML:
   ```xml
   <Report name="Finance_FortisFees" type="PyScript" role="Finance" />
   ```

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
