# Program Pulse

Scheduled digest reports that surface what's happening across your programs and divisions. New enrollments, dropped members, attendance gaps, transactions, baptisms, new members, stale involvements — delivered to the right people on the day you choose.

With this tool, leaders can:

- Monitor activity across multiple programs and divisions from a single configuration
- Track new enrollments, drops, baptisms, new church members, and new people records
- Detect attendance gaps — people who attended regularly but have stopped showing up
- Identify stale involvements with no recent meeting activity
- See transaction summaries (fees paid, balances due) per organization
- Choose detail level per section (Detail, Summary, or None) to tailor reports for each audience
- Schedule automatic sending on any day of the week via MorningBatch
- Send manual reports on demand with one click
- Configure contact method tracking (Phone, Email, Visit, etc.) linked to TouchPoint keywords
- View outreach effort breakdown in the attendance gaps section
- Preview reports before sending
- Review full send history with error tracking

---

## Configurations Tab

Create and manage report configurations. Each configuration defines which programs to monitor, what sections to include, who receives the report, and when it sends. Multiple configurations can run independently — one per ministry area, audience, or schedule.

<!-- <p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Program%20Pulse/PP-Configs.png" width="700" alt="Program Pulse - Configurations">
</p> -->

---

## Configuration Editor

Set lookback days, stale thresholds, attendance gap windows, and scheduled send days. Select programs and divisions to monitor, choose detail levels for each report section, and add recipients. A single help toggle in the header reveals descriptions for every field.

<!-- <p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Program%20Pulse/PP-Editor.png" width="700" alt="Program Pulse - Configuration Editor">
</p> -->

---

## Report Preview

Preview any configuration's report before sending. The preview shows exactly what recipients will see in their email, using live data from your TouchPoint database.

<!-- <p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Program%20Pulse/PP-Preview.png" width="700" alt="Program Pulse - Report Preview">
</p> -->

---

## Attendance Gaps

People who attended 3+ times in the prior 6 months but have stopped attending are flagged with lapse rates per involvement. The report shows whether they moved to another monitored involvement or are disengaged, plus a breakdown of contact efforts from task/note records using configurable contact method codes.

<!-- <p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Program%20Pulse/PP-Gaps.png" width="700" alt="Program Pulse - Attendance Gaps">
</p> -->

---

## Report Sections

| Section | Description |
|---------|-------------|
| New Enrollments | People who joined an organization during the lookback period |
| Dropped Members | People whose membership was inactivated during the period |
| New Involvements | Organizations created within monitored programs |
| Stale Involvements | Active organizations with no meeting activity beyond the stale threshold |
| Transactions | Payment activity (fees paid, balances due) within monitored organizations |
| New People | Person records created during the period connected to monitored organizations |
| New Baptisms | People with baptism dates during the period |
| New Church Members | People with join dates during the period with member status |
| Attendance Gaps | People who previously attended regularly but have stopped |

---

## Content Storage

| Content Name | Description |
|-------------|-------------|
| ProgramPulse_Configs | All report configurations (programs, recipients, sections, schedules) |
| ProgramPulse_Settings | Global settings (default sender, contact methods) |
| ProgramPulse_Log | Send history (last 100 entries) |

These are created automatically and persist independently of the script code.

---

## Setup

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**
3. Name it `TPxi_ProgramPulse`
4. Paste the contents of `TPxi_ProgramPulse.py`
5. Access the dashboard at `/PyScript/TPxi_ProgramPulse`
6. Set a default sender in **Settings**

### Automatic Sending (Optional)

Open your **MorningBatch** script in Special Content > Python and add:

```python
Data.run_batch = "true"
model.CallScript("TPxi_ProgramPulse")
```

Reports will only send on each configuration's scheduled day.

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
