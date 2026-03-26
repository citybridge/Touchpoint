# QuickLinks

A 2-part system for managing and displaying customizable quick-access links on your TouchPoint homepage. Admins configure links, categories, subgroups, and count badges through a visual admin UI.  Users see a clean, permission-filtered widget on their dashboard.

With this tool, you can:

- Organize links into collapsible categories with role-based visibility
- Display count badges from live SQL queries (open tasks, member counts, etc.)
- Group large categories into inline subgroups or clickable popup tiles
- Nest popup subgroups inside inline subgroups for cleaner organization
- Auto-hide seasonal links with expiration dates
- Drag-and-drop to reorder everything — no manual priority numbers
- Manage all configuration through a visual admin UI with guided tour
- Backup and restore configurations with full version history

---

## Widget (Part 1 — TPxi_QuickLinks)

The homepage widget that displays your configured links. Categories expand/collapse, icons show count badges, and everything respects role permissions. Subgroups organize large categories into sections or clickable popup menus.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Quicklinks/QL1.png" width="400" alt="QuickLinks Widget on Homepage">
</p>

---

## Admin UI (Part 2 — TPxi_QuickLinksAdmin)

A visual admin interface for managing the widget configuration. The unified Structure tab shows categories, subgroups, and links in a collapsible tree with drag-and-drop reordering. Includes a guided tour for first-time users and inline help tooltips on every form field.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Quicklinks/QL2.png" width="700" alt="QuickLinks Admin - Structure Tab">
</p>

---

## Icon Configuration

Each link is configured with a label, URL, icon, category, optional subgroup, role permissions, count query, org ID, and expiration date. Inline help tooltips explain every field.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/QuickLlinks/QL3.png" width="500" alt="QuickLinks Admin - Icon Configuration Modal">
</p>

---

## Count Queries

Define SQL queries that display live count badges on icons. Queries can reference an organization ID or the current user's ID. Test queries directly from the admin UI.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Quicklinks/QL4.png" width="700" alt="QuickLinks Admin - Count Queries Tab">
</p>

---

## How It Works

| Part | Script Name | Purpose |
|------|------------|---------|
| Widget | TPxi_QuickLinks | Displays links on the homepage |
| Admin | TPxi_QuickLinksAdmin | Visual UI to manage configuration |

Both scripts share the same JSON config stored in Special Content as `QuickLinksConfig`. The admin writes it; the widget reads it.

---

## Setup

### Part 1 — Widget

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**, name it `TPxi_QuickLinks`
3. Add `widget` to the content keywords
4. Paste the contents of `TPxi_QuickLinks.py`
5. Go to **Admin > Advanced > Homepage Widget**
6. Select the script, add a name, and set permissions

### Part 2 — Admin UI

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**, name it `TPxi_QuickLinksAdmin`
3. Paste the contents of `TPxi_QuickLinksAdmin.py`
4. Add to CustomReports XML:
   ```xml
   <Report name="TPxi_QuickLinksAdmin" type="PyScript" role="Admin" />
   ```

---

## Configuration Features

| Feature | Description |
|---------|-------------|
| Categories | Top-level groups with icons, expand/collapse, and role filtering |
| Links/Icons | Individual items with label, URL, icon, count badge, and expiration |
| Subgroups | Organize links within categories — inline sections or popup tiles |
| Nested Subgroups | Popup subgroups can nest inside inline subgroups |
| Count Queries | SQL queries that show live count badges on icons |
| Role Permissions | Filter visibility at both category and individual link level |
| Drag-and-Drop | Reorder categories, subgroups, and links by dragging |
| Expiration Dates | Auto-hide seasonal links after a set date |
| Guided Tour | First-time walkthrough with step-by-step highlights |
| Inline Help | Hover tooltips on every form field in the admin UI |
| Backup/Restore | Automatic backups before every save with one-click restore |
| Import/Export | Import starter defaults or export JSON for migration |

---

## Backup System

Backups are created automatically before every save. Up to 10 backups are kept, each logging who made the change and when. Backups can be previewed and restored with one click, and a safety backup of the current content is created before any restore.

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
