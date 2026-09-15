# Ferry Ticket Counts

Ferries to Toronto Island Park operate year-round out of Jack Layton Ferry Terminal. Ferries carry passengers to and from Centre Island, Hanlan’s Point and Ward’s Island. There are limited amenities during the off-season.

This dataset provides near real-time information on ferry ticket sales and ticket redemptions. The counts are provided in 15-minute intervals and are updated hourly. They encompass all product types and include both online and POS-kiosk sales.

This dataset is prepared for MSE 121 at the University of Waterloo as an example dataset for learning to work with data at the command line and in Python. The data is designed and modified specifically for MSE 121 homework practice and should not be used for academic or industry research outside the context of this course.


## Files

| file              | rows   |
|-------------------|--------|
| `ferry-ticket-counts.csv`    | 279573   |


### `ferry-ticket-counts.csv`

A plain CSV file (comma-separated values, one header row, and no quoting). No field contains a comma, so the file can be split on commas with any tool. The first few rows are provided.

```
_id,Timestamp,Redemption Count,Sales Count
1,2026-08-22T10:45:00,9,2
2,2026-08-22T10:30:00,331,274
3,2026-08-22T10:15:00,277,199
```

Each row represents the ticket sales for a specific 15-minute interval. Rows are sorted in numerical order by `_id`.

| column | meaning |
|---|---|
| `_id`| A unique identifier for each row. |
| `Timestamp` | The date and time of the 15-minute interval. |
| `Redemption Count` | The number of tickets that were redeemed during the 15-minute interval. |
| `Sales Count` | The number of tickets that were purchased during the 15-minute interval. |


## Things to know before you compute anything

**Sales versus redemptions.** Sales represent the number of customers that buy a ticket from either the POS-kiosk or online during a 15-minute interval, while redemptions track the number of tickets that were redeemed during that time.

**Individual customer actions.** Some customers may purchase and redeem a ticket within the same 15-minute interval, or may purchase it first, then redeem it later in the day. There is no way to know the actions of a specific customer.


## Source

City of Toronto open data, *Toronto Island Ferry Ticket Counts*, published once by Fleet Services:

<https://open.toronto.ca/dataset/toronto-island-ferry-ticket-counts/>

Licensed under the [Open Government Licence - Toronto](https://www.toronto.ca/city-government/data-research-maps/open-data/open-data-licence/). *Contains
information licensed under the Open Government Licence - Toronto.*


## How these files differ from the source

The City publishes the dataset in either CSV, JSON, or XML format. Only the CSV format is provided.

No other changes were made between this version of the dataset and the source.
