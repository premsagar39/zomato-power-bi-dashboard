# Data dictionary

## Restaurants.csv — Power BI table `zomato`

| Column | Meaning |
| --- | --- |
| RestaurantID | Unique restaurant identifier and relationship key |
| RestaurantName | Restaurant name as supplied |
| CountryCode / Country | Source country identifier and mapped country name |
| City | Source city name |
| Cuisines | Original comma-separated cuisine labels; can be blank |
| Currency | Local currency for the recorded cost |
| Has_Table_booking | Table booking availability: Yes / No |
| Has_Online_delivery | Online delivery availability: Yes / No |
| Price_range | Source ordinal price range, 1–4 |
| Votes | Recorded votes; not orders or customers |
| Average_Cost_for_two | Recorded cost for two in local currency |
| Rating | Recorded source rating; the meaning of exactly 1.0 is unverified |
| PriceTier | Label derived from Price_range |
| EngagementBand | Descriptive vote band; not a prediction |
| ServiceProfile | Combination of booking and online delivery availability |
| RatingBand | Descriptive rating band that preserves the special 1.0 value |

## RestaurantCuisine.csv

| Column | Meaning |
| --- | --- |
| RestaurantID | Key referencing a restaurant |
| Cuisine | Trimmed cuisine label; blank source cuisines use Unspecified |

Each restaurant–cuisine pair is unique. There are 19,714 pairs and 146 labels including Unspecified. Filtering several cuisines selects matching restaurants; it does not require every selected cuisine to be present.

## Analysis definitions

- **Engaged restaurant:** at least 100 recorded votes, a chosen exploratory threshold.
- **Delivery gap:** engaged restaurant whose online delivery flag is No.
- **Delivery coverage:** restaurants offering online delivery divided by selected restaurants.
- **City delivery coverage index:** city coverage divided by coverage across the selected cities.
- **City vote engagement index:** city votes per restaurant divided by votes per restaurant across the selected cities.
- **India positive cost:** CountryCode = 1 and Average_Cost_for_two > 0.
