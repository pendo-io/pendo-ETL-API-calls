# pendo-ETL-API-calls

## Overview
The API calls outlined in this repository are for use with Pendo's v1 REST Aggregations API. Aggregations are a query language for accessing and processing Pendo data. They take sources of Pendo data and apply operators to do computations. They run in the context of a given Pendo subscription and are written in JSON.

These requests are focused on data you might want to use in your broader BI environment.  They are intended to show you what's possible when you combine Pendo data with other data sources (eg. Saleforce.com, Marketo, ERP, etc.) to visualize the impact of tracking, guiding and polling users of your application via Pendo.

## Common Request Information

### Endpoint
`https://app.pendo.io/api/v1/aggregation`

### Headers

Authentication of requests is handled by an integration key. When enabled for the subscription, admins can create and manage those keys [here](https://app.pendo.io/admin/integrationkeys). Integration keys should be kept secret! It is how you securely access and update information about your users and accounts in Pendo. Do not share them in client-side javascript, publicly accessible code repositories, etc.

If you do not have access to Integration Keys in your subscription, please reach out to your Customer Success Manager or help@pendo.io.

All requests require the following headers:
```json
Content-Type: application/json
X-Pendo-Integration-Key: <YOUR_KEY>
```

### Body
Request bodies are provided in each example's folder.

## Additional Documentation

Our full v1 API documentation can be found [here](https://engageapi.pendo.io/).
