# Zomato Restaurant Insights

A Power BI analysis of 9,551 restaurant listings across 15 countries and 141 cities, comparing cuisines, pricing, ratings and service availability.

![Zomato Restaurant Insights dashboard](reports/figures/dashboard_overview.png)

**Power BI · Power Query · Data Modeling · DAX**

## Findings

- 2,451 restaurants offer online delivery: 25.7% of the sample.
- Among 2,826 listings with at least 100 votes, 1,762 have no online delivery.
- North Indian cuisine appears at 3,960 restaurants; one restaurant can belong to several cuisines.
- Median positive cost for two in India is INR 450.

## Report

The five pages cover Overview, Markets, Services & Pricing, Delivery Gaps and Restaurant List. The overview centres on service availability, with surrounding city and price charts. Detail pages use vertical KPIs and wider comparison tables.

The report contains 43 DAX measures, country and city filters, ranking and metric views, contextual tooltips and restaurant drillthrough. City benchmark index 1.00 represents the selected market average.

## Explore

- [Download the PBIX](dashboard/Zomato_Insights.pbix)
- [43 DAX measures](dax/measures.dax)
- [Editable report definition](powerbi/Zomato_Insights.Report)
- [Delivery-gap comparison](reports/figures/zomato-4.png)
- [Data dictionary](docs/data-dictionary.md)
- [Light and dark themes](powerbi/themes)

## Open and refresh

1. Download the repository and open `dashboard/Zomato_Insights.pbix` in Power BI Desktop. Its imported snapshot can be viewed without refreshing.
2. To refresh, open **Transform data** and change the Source paths for `zomato` and `RestaurantCuisine` to the extracted `data/Restaurants.csv` and `data/RestaurantCuisine.csv` files.
3. Retain UTF-8 encoding, transformations and column types, then apply and refresh. In Desktop edit mode, use Ctrl+click on report navigation buttons.

`zomato` has one row per restaurant. The cuisine bridge has one unique restaurant–cuisine pair per row and filters restaurants through `RestaurantID`. Distinct restaurant counts avoid duplicate counting.

## Data notes

These are historical listings, heavily concentrated in India. Votes indicate recorded engagement, not orders or verified demand. Cuisine counts overlap; cross-country prices use different currencies, so INR pricing measures are restricted to India. Zero costs are excluded only from measures named “Positive Cost”; source ratings are retained as recorded.

The prepared CSVs come from the Zomato workbook used for this study. The original publication date and dataset redistribution license have not been confirmed.
