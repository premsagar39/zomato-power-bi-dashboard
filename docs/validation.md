# Validation notes

## Source and model checks

- Compared all 9,551 restaurant IDs across 11 analysis fields with the supplied workbook: 105,061 matching field values and no mismatches.
- Checked unique restaurant keys and cuisine membership counts.
- Verified the saved model contains 43 measures and the report contains five pages.
- Queried the native model to confirm 1,064 engaged delivery listings and 1,762 engaged listings without delivery.
- Verified a city with no delivery matches returns zero for the delivery count.

## Interactive checks in Power BI Desktop

- The final PBIX opened and was saved successfully in Power BI Desktop.
- Selecting India changed the listing count to 8,652 and updated the city benchmarks.
- New Delhi's delivery index changed from 1.06 for the full selection to 0.97 for India; its vote index changed from 0.73 to 0.84.
- Checked a North Indian cuisine tooltip: 3,960 restaurants, 28.8% delivery coverage, average source rating 2.75, and delivery gap 581.
- Verified city count data bars use a zero minimum and persist in the saved report.
- Reset filters to the full sample and saved the report on Overview.

## Reference totals

| Check | Value |
| --- | ---: |
| Restaurants | 9,551 |
| Countries | 15 |
| Cities | 141 |
| Total votes | 1,498,645 |
| Online delivery | 2,451 |
| Table booking | 1,158 |
| Both services | 435 |
| At least 100 votes | 2,826 |
| Engaged with delivery | 1,064 |
| Engaged without delivery | 1,762 |
| Zero votes | 1,094 |
| Rating exactly 1.0 | 2,148 |
| Zero costs | 18 |
| Missing source cuisines | 9 |

These are consistency and interaction checks, not confirmation of the source dataset's real-world completeness or freshness. Refresh on another computer requires updating the two source file paths.
