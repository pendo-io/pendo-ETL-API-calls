# Page - Feature - Guide IDs and their Human-readable Names

For the Pendo Usage Looker Block example, please download and use the following API call bodies:

- allPages
- allFeatures

Follow the instructions in the Block to leverage these API calls for table builds needed to support the Looker Dashboard.

Alternatively, use them and the allGuides API call to explore this data for your own non-Looker purposes.

All of these API calls use the following:

POST https://app.pendo.io/api/v1/aggregation

### Using headers:

Content-Type: application/json

X-Pendo-Integration-Key: $insert-pendo-key$

The request bodies in this folder will generate responses that provide you with the internal Pendo ID values for pages, features and guides as well as the human-readable names assigned to those IDs.  

The output from these requests can be useful to include in your ETL jobs so you can periodically load tables for each into your BI environment then join these tables to get human-readable values for these objects when you don't already have them in other API call request bodies.
