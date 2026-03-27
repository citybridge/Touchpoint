# Find Funds in Batch

A simple finance utility that finds which batches contain contributions to a specific fund within a date range. Useful for tracking down deposits, reconciling fund activity, or auditing batch assignments.

With this tool, you can:

- Search for all batches containing a specific contribution fund
- Filter by date range to narrow results
- See batch ID, header type, status, and deposit date
- Click through to the batch detail page directly from results
- Fund dropdown is auto-populated from your TouchPoint contribution funds

---

## Fund Search

Select a fund and date range to find all batches that contain contributions to that fund. Results link directly to the batch detail page in TouchPoint.

<p align="center">
  <img src="https://github.com/bswaby/Touchpoint/raw/main/TPxi/Find%20Funds%20in%20Batch/FindFundsinBatch.png" width="700" alt="Find Funds in Batch">
</p>

---

## Setup

1. Navigate to **Admin > Advanced > Special Content > Python**
2. Click **New Python Script File**, name it `TPxi_FindFundsinBatch`
3. Paste the contents of `TPxi_FindFundsinBatch.py`
4. Add to CustomReports XML:
   ```xml
   <Report name="TPxi_FindFundsinBatch" type="PyScript" role="Finance" />
   ```

---

*Like this tool? [DisplayCache](https://displaycache.com) integrates directly with TouchPoint and helps fund continued development of tools like this one.*
