# Volunteer Widget

A homepage dashboard widget that shows the logged-in user their upcoming volunteer assignments from TouchPoint's Scheduler. Displays service dates, team names, subgroup positions, and fill status — giving volunteers a quick view of when and where they're serving next.

With this tool, you can:

- Show each user their upcoming volunteer schedule on the homepage
- Display service date, time, team, subgroup/position, and who else is serving
- Show fill status (e.g. "2 of 3") for each position
- Link to the full Scheduler Report for detailed views
- Link to your church's serve page for users not yet volunteering
- Works with TouchPoint's Scheduler (RegistrationTypeId 22)

---

## Widget View

The widget appears on the TouchPoint homepage showing the logged-in user's upcoming volunteer assignments, grouped by date with team and position details.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Volunteer%20Widget/WidgetVolunteer.png" width="400" alt="Volunteer Widget">
</p>

---

## Configuration

Two settings at the top of the script:

| Setting | Description |
|---------|-------------|
| `serveOpportunitiesLink` | URL to your church's serve/volunteer page (shown when user has no assignments) |
| `SchedulerReportPythonScriptName` | Name of your Scheduler Report python script for the "View Full Schedule" link |

---

## Related

This widget is designed to work with the [Scheduler Report](https://github.com/bswaby/Touchpoint/tree/main/Blue%20Toolbar/Scheduler%20Report) script, which provides the full schedule view that the widget links to.

---

## Setup

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**, name it (e.g. `Volunteer_Widget`)
3. Add `widget` to the content keywords
4. Paste the contents of `Volunteer_Widget.py`
5. Update the two config variables at the top
6. Go to **Admin > Advanced > Homepage Widgets**
7. Click **Add Widget**, select the script under Code (Python)
8. Add a name, description, select role(s), save, and enable

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
