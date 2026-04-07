### 📊 [Enterprise Report Builder](https://github.com/bswaby/Touchpoint/tree/main/TPxi/Enterprise%20Reporting)
133 built-in reports across 10 categories — Demographics, Financial, Attendance, Membership, Engagement, Communications, Transactions, Tasks, Emergency, and Admin all in a single paste-and-go script with auto-updates via DisplayCache.

- ⚙️ **Implementation Level:** Easy
- 🧩 **Installation:** Single script. Paste into Special Content > Python, navigate to `/PyScript/EnterpriseReporting`. Configure settings via the gear icon.

<summary><strong>Features</strong></summary>

- **133 Built-in Reports:** Pre-built SQL across 10 categories — no query writing needed
- **AG Grid Tables:** Sortable, filterable, paginated data grids with column resizing
- **Chart.js Visualizations:** Line, bar, pie, and doughnut charts with automatic data mapping
- **Smart KPI Cards:** Auto-generated aggregate insights — averages, totals, top categories, and ranges based on data shape
- **Blue Toolbar Integration:** Run any report on selected people from a search
- **Bulk Actions:** Tag, Task, or Note selected people directly from report results
- **Person Detail Popup:** Click any name to see engagement score, milestones, family, involvements, and journey timeline
- **Person Engagement Scorecard:** Per-person breakdown of 4 scored engagement factors (recency, frequency, groups, serving)
- **Priority Outreach List:** 9-factor weighted priority scoring inspired by Prospect Builder
- **Milestone Pipeline:** Track where people stall on the discipleship pathway (attend → decision → baptism → membership → serving)
- **Family Engagement Gap:** Identify households where some members are engaged but others are not
- **Journey Stage Distribution:** Congregation-wide engagement tier breakdown with doughnut chart
- **Current & Past Involvements:** Per-person involvement detail with attendance stats and tenure tracking
- **Contact Effort Tracking:** Configure outreach methods (Phone, Email, Visit, Text, Mail) and every people report automatically shows per-method contact counts from TaskNotes
- **Fund Multi-Select Filters:** Filter financial reports by one or multiple funds
- **Custom Report Builder:** Create and save your own SQL reports with a built-in editor and snippet library
- **CSV Export & Print:** One-click export or pop-up print for any report
- **Per-Report Permissions:** Restrict individual reports beyond category-level roles
- **Auto-Update:** Checks DisplayCache for new versions (Admin/Developer only) and updates in-place
- **Role-Based Access:** Control who sees each category and each individual report
- **Inv. Scope Filter:** Filter any report by a specific involvement's membership

<summary><strong>Report Categories</strong></summary>

| Category | Count | Highlights |
|----------|-------|------------|
| **Demographics** | 10 | Age, Gender, Campus, Family, Marital, Zip Code, Decisions, Resident Code |
| **Financial** | 20 | Giving by Fund, Weekly Giving, Donor Segments, 5-Year History, YoY Comparison, Giver Groups, Lapsed Givers, Fund Health, Contributions by Age Bin |
| **Attendance** | 10 | By Program, Percentage, Weekly Trends, Division Breakdown |
| **Membership** | 12 | New Members, Baptism Statistics, Growth Trends, Retention Cohort, Lifecycle Stages |
| **Engagement** | 35 | Person Scorecard, Priority Outreach, Milestone Pipeline, Family Engagement Gap, Journey Stages, Current/Past Involvements, Churn Report, First-Time Guests, Guest Retention, Lapsed Adults/Children, Attendance Gaps, Group Growth, Volunteer Burnout Risk, Unconnected Members |
| **Communications** | 12 | Email Stats, SMS Campaigns, Bounce Rates, Pending Queue, Sender Analytics |
| **Transactions** | 6 | Payment history, fee tracking, transaction search |
| **Tasks** | 8 | Task/Note activity, completion velocity, overdue tracking, team workload |
| **Emergency** | 1 | Contact List with medical info — print-optimized |
| **Admin** | 14 | Login Activity, User Accounts, Stale Accounts, Activity by Category, Change Logs |

<hr>
<summary><strong>AG Grid with Filters</strong></summary>
<p>Sortable, filterable tables with clickable person names</p>
<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Enterprise%20Reporting/ER-1.png" width="700">
</p>

<summary><strong>Chart Visualizations</strong></summary>
<p>Line, bar, pie, and doughnut charts with automatic data mapping</p>
<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Enterprise%20Reporting/ER-2.png" width="700">
</p>

<summary><strong>Settings</strong></summary>
<p>Category roles, per-report permissions, contact method keywords, and more</p>
<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Enterprise%20Reporting/ER-3.png" width="700">
</p>

<summary><strong>Auto-Update</strong></summary>
<p>Admin and Developer roles get notified when a new version is available</p>
<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Enterprise%20Reporting/ER-4.png" width="700">
</p>

<summary><strong>Installation</strong></summary>

1. **Admin > Advanced > Special Content > Python**
2. Click **Add New**, name it `EnterpriseReporting`
3. Paste the script and Save
4. Navigate to `/PyScript/EnterpriseReporting`
5. (Optional) Click settings to configure category roles, contact methods, and fiscal year

<summary><strong>Settings Overview</strong></summary>

| Setting | Description |
|---------|-------------|
| **Fiscal Year Start Month** | Used by "Fiscal Year to Date" filter presets |
| **AG Grid Enterprise** | Enable pivot tables, row grouping, Excel export (requires license) |
| **Category Access Roles** | Comma-separated TouchPoint roles per category |
| **Per-Report Permissions** | Override category roles for individual reports |
| **Contact Effort Tracking** | Enable/disable, set lookback period, configure method keywords |
| **Contact Method Keywords** | Map codes (P, E, T, V, M) to TouchPoint TaskNote keywords |

<summary><strong>Blue Toolbar</strong></summary>

Add to **Special Content > Text Content > CustomReports**:
```xml
<Report name="EnterpriseReporting" type="PyScript" role="Access" />
```

---
*Written by [Ben Swaby](https://github.com/bswaby). These tools are free because they should be. If they've saved you time, consider [DisplayCache](https://displaycache.com) — church digital signage that integrates with TouchPoint.*
