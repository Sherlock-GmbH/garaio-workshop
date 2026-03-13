# Todo

## Bug #191 - Auftragsbeginn einen Tag zurück
- **State:** Committed | **Priority:** 2 | **Severity:** Medium
- **Iteration:** CRs 2025
- **Created:** 2024-11-12 (Stephan Stutz) | **Activated:** 2025-04-28 (Jan Stohler)
- **Issue:** Bei Umwandlung Offerte -> angenommen (Vertrag erstellen), Auftragsbeginn-Datum fällt nach Speichern um 1 Tag zurück. Likely UTC/timezone off-by-one.

### Azure DevOps commands
```bash
# list all open work items
az boards query --wiql "SELECT [System.Id], [System.Title], [System.State], [System.WorkItemType] FROM workitems WHERE [System.State] <> 'Closed' AND [System.State] <> 'Done' AND [System.State] <> 'Removed' ORDER BY [System.CreatedDate] DESC" --organization https://dev.azure.com/garaio-allpura --project Kalkulationstool --output table

# list open bugs only
az boards query --wiql "SELECT [System.Id], [System.Title], [System.State], [System.WorkItemType] FROM workitems WHERE [System.WorkItemType] = 'Bug' AND [System.State] <> 'Closed' AND [System.State] <> 'Done' ORDER BY [System.CreatedDate] DESC" --organization https://dev.azure.com/garaio-allpura --project Kalkulationstool --output table

# show single work item details
az boards work-item show --id <ID> --organization https://dev.azure.com/garaio-allpura --output json
```
