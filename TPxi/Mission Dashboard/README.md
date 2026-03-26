# Missions Dashboard

A comprehensive mission trip management dashboard for TouchPoint with sidebar navigation, role-based access, real-time budget tracking, and team management. Designed for both missions directors who manage all trips and trip leaders who manage their own.

With this tool, you can:

- View all active and upcoming mission trips from a single dashboard
- Track trip budgets, fundraising progress, and individual payments
- Manage team rosters with leader/member designations
- Schedule and track trip meetings with attendance
- Send payment reminder emails directly from the dashboard
- Adjust fees and process transactions (with finance role)
- View trip-level messaging and communication history
- Configure dashboard behavior and excluded organizations
- Role-based views — admins see everything, leaders see their trips

---

## Dashboard Home

The main view shows all active mission trips with key metrics. Team size, dates, fundraising progress, and upcoming deadlines. The sidebar navigation provides quick access to any trip's details. Mobile-responsive with a collapsible sidebar.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Missions%20Dashboard/MD1.png" width="700" alt="Missions Dashboard - Home">
</p>

---

## Statistics

Aggregated statistics across all mission trips.  Total participants, upcoming trips, budget summaries, and trend data. Gives missions directors a high-level view of the program.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD2.png" width="700" alt="Missions Dashboard - Statistics">
</p>

---

## Calendar

A visual calendar showing all mission trip dates, meetings, and deadlines. Quickly see what's coming up across all trips.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD3.png" width="700" alt="Missions Dashboard - Calendar">
</p>

---

## Trip Overview

Detailed view of a single trip.  Dates, location, description, team count, budget status, and key contacts. The starting point for managing any trip.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD4.png" width="700" alt="Missions Dashboard - Trip Overview">
</p>

---

## Team Members

View and manage the trip roster. Shows each team member with their role, contact info, and payment status. Leaders are highlighted separately from regular members.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD5.png" width="700" alt="Missions Dashboard - Team Members">
</p>

---

## Meetings

Track trip meetings with dates, attendance, and notes. See who attended each preparation meeting and identify members who may need follow-up.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD6.png" width="700" alt="Missions Dashboard - Meetings">
</p>

---

## Budget & Fundraising

Real-time budget tracking with fundraising progress bars for each team member. See who has paid in full, who is behind, and the overall trip financial health.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD7.png" width="700" alt="Missions Dashboard - Budget and Fundraising">
</p>

### Payment Reminder Emails

Send payment reminder emails directly from the budget view. Select individuals or send bulk reminders to everyone with an outstanding balance.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD8.png" width="500" alt="Missions Dashboard - Payment Reminder Email Modal">
</p>

### Fee Adjustments

Adjust individual trip fees for scholarships, early-bird discounts, or special circumstances. Requires a finance role (Finance, FinanceAdmin, or ManageTransactions).

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD9.png" width="500" alt="Missions Dashboard - Fee Adjustment">
</p>

---

## Messages

View trip-level communication history. See emails sent to the trip team and compose new messages.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD10.png" width="700" alt="Missions Dashboard - Messages">
</p>

---

## Settings

Configure dashboard behavior.  Excluded organization IDs, role mappings, UI preferences, and debug options. Settings are stored in the script's Config class.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Mission%20Dashboard/MD11.png" width="700" alt="Missions Dashboard - Settings">
</p>

---

## Role-Based Access

| Role | Access Level |
|------|-------------|
| Edit / Admin / Finance / MissionsDirector | Full access to all trips and financial data |
| Trip Leader (MemberType 140/310/320) | Access to assigned trips only, payment totals visible |
| Finance / FinanceAdmin / ManageTransactions | Required for fee adjustments and financial modifications |

Leaders without menu-access roles can reach the dashboard via direct link. They see only their assigned trips with privacy-filtered financial data (totals but not individual giver details).

---

## Setup

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**, name it `TPxi_MissionsDashboard`
3. Paste the contents of `TPxi_MissionsDashboard.py`
4. Update the `Config` class at the top of the script for your environment:
   - `APPLICATION_ORG_IDS` — organization IDs to exclude
   - `ADMIN_ROLES` — roles that get full access
   - `FINANCE_ROLES` — roles that can modify financial data
5. Add to CustomReports XML:
   ```xml
   <Report name="TPxi_MissionsDashboard" type="PyScript" role="Access" />
   ```

---

## Performance

Queries are optimized to load in ~1 second (down from 47 seconds in earlier versions). Detailed trip data loads via AJAX on demand, so the initial dashboard renders quickly even with many active trips.

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
