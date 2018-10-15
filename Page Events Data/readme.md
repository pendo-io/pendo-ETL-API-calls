# Page Events Data

This `pageEvents.json` request body will generate a response that provides detailed page event data for a visitor by account.  The number of events and minutes spent are summed by day.

POST https://app.pendo.io/api/v1/aggregation

### Using headers:

Content-Type: application/json

X-Pendo-Integration-Key: $insert-pendo-key$

## Important:

The current request body is set to collect data for the day before the day the API call is executed.  You can gather data for a longer period of time by changing this value from 1 to some other value.

Please **DO NOT** set the value to something greater than 30 as it will retrieve a large data set that could impact performance.  Instead, we ask that you keep the value set to 1 and run your ETL process daily then append the data to the table in which you're loading it.
