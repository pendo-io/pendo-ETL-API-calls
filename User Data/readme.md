# Visitor and Account Data API Calls

For the Pendo Usage Looker Block example, please download and use the following API call bodies:

- Visitors
- Accounts

Follow the instructions in the Block to leverage these API calls for table builds needed to support the Looker Dashboard.

Alternativel, use them and the following API calls to explore Visitor and Account data for your own non-Looker purposes.

All of these API calls use the following:

POST https://app.pendo.io/api/v1/aggregation

### Using headers:

Content-Type: application/json

X-Pendo-Integration-Key: $insert-pendo-key$

## Anonymous Visitors

This API call enables you to pull all of the Pendo designated Anonymous Visitors from your subscription.

## New Users Last X Days

This API request will pull visitor IDs and first visit timestamp for all new users in the last 7 days.

### Options for the API call

The current request body is set to query for new users the last 7 days.  You can set the value of 7 to 30, 60, 180 by simply replacing 7 in the "filter" in the request body.

This request body example also provides a simple hash of visitorId for PII reasons.  If you don't want to hash the visitorId simply remove the "eval" statement that includes the visitorId hash from the request body.
