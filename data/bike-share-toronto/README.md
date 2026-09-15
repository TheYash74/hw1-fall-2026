# Toronto Bike Share Usage

Bike Share Toronto operates as a point-to-point network, allowing riders to pick up a bicycle at any station across the city and return it to any other destination dock.

This dataset is prepared for MSE 121 at the University of Waterloo as an example dataset for learning to work with data at the command line and in Python. The data is designed and modified specifically for MSE 121 homework practice and should not be used for academic or industry research outside the context of this course.


## Files

| file              | rows   |
|-------------------|--------|
| `stations.csv`    | 1061   |
| `trips.csv`       | 695724 |


### `stations.csv`

A plain CSV file (comma-separated values, one header row, and no quoting). No field contains a comma, so the file can be split on commas with any tool. The first few rows are provided.

```
station_id,name
7000,Fort York  Blvd / Capreol Ct
7001,Wellesley Station Green P
7002,St. George St / Bloor St W
```

Each row represents a station's details. Rows are sorted in numerical order by `station_id`.

| column | meaning |
|---|---|
| `station_id`| A unique identifier for each station. |
| `name` | The name of a station. |


### `trips.csv`

A plain CSV file (comma-separated values, one header row, and no quoting). No field contains a comma, so the file can be split on commas with any tool. The first few rows are provided.

```
duration_seconds,start_station_id,start_time,end_station_id,end_time,bike_id,user_type_code,bike_model_code
528,7041,2024-01-01 00:00:08,7130,2024-01-01 00:08:56,7855,C,G
973,7105,2024-01-01 00:12:42,7048,2024-01-01 00:28:55,4220,C,I
796,7788,2024-01-01 00:20:35,7076,2024-01-01 00:33:51,5872,M,I
```

Each row represents a trip between two stations. Rows are sorted in numerical order by `start_time`.

| column | meaning |
|---|---|
| `duration_seconds` | The length of a trip (in seconds). |
| `start_station_id` | The ID of the starting station. The name of this station can be found in the `stations.csv` file. |
| `start_time` | The start time of the trip. |
| `end_station_id` | The ID of the ending station. The name of this station can be found in the `stations.csv` file. |
| `end_time` | The end time of the trip. |
| `bike_id` | The ID of the bike that was used. |
| `user_type_code` | The type of user who took the trip (C=Casual or M=Member). |
| `bike_model_code` | The type of bike that was used (A=ASTRO, E=EFIT, G=EFIT G5, or I=ICONIC). |


## Things to know before you compute anything

**`end_time` is redundant.** It equals `start_time` plus `duration_seconds`. In cases where the two disagree by exactly one hour, those are the daylight saving changeovers.

**There is no trip identifier.** Row order is the only thing tying a row to its source. The build verifies the split by rebuilding every original row and comparing positionally.

**A trip is one row.** A trip represents one dock to another dock. It is common for a rider to re-dock and continue, which appears as two unrelated rows. The data has no notion of a journey.


## Source

City of Toronto open data, *Bike Share Toronto Ridership Data*, published by the Toronto Parking Authority and refreshed annually:

<https://open.toronto.ca/dataset/bike-share-toronto-ridership-data/>

Licensed under the [Open Government Licence - Toronto](https://www.toronto.ca/city-government/data-research-maps/open-data/open-data-licence/). *Contains
information licensed under the Open Government Licence - Toronto.*


## How these files differ from the source

The City publishes one Excel workbook (or zip file) per year. This dataset particularly pertains to the 2024 dataset. What changed:

- **Data subset.** To reduce the total number of rows to process, a 10% random sample of the 2024 dataset was extracted (taken row by row with `random.Random(121)` for reproducibility).
- **`User_Type` and `Bike_Model`.** Both values became one-character codes. A value with no code stops the build rather than being absorbed silently.
- **Dropped `Trip_Id`.** It represents the operator's own unique identifier, but costs 6.5% of the file and does not provide anything useful for our purposes.
- **`end_station` fixes.** End stations written as `7130.0` were repaired to `7130`. A blank end station is left blank; some trips were never docked.
- **Column names were made plain.** `Trip_Duration` became `duration_seconds`, and all other columns were updated to snake_case.
