# NPS Responses

## 1. Get Poll IDs

Using the `getPollIds.json` request, insert the `yourGuideId` value. This value can be found by navigating to the guide details view in Pendo. You will notice the URL is of the form `https://app.pendo.io/guides/pnsd2f9FBXwgDDqEdpKaV-ueMXA` where `pnsd2f9FBXwgDDqEdpKaV-ueMXA` is `yourGuideId`. Running this request will return the two poll IDs you will need for the next request.

## 2. Plug Poll IDs into second request

### combinedNpsResponses.json request
You will need to substitute the overall guide ID that you located in the first step in for the `yourGuideId` variables. NPS Polls are actually considered two separate polls in the Pendo backend, which is why you have two poll IDs for both the quantitative response (0-10) and qualitative responses. Substitute these values in for `pollId1` and `pollId2` respectively.

### Aggregation Breakdown

This request utilizes `spawn` which allows you to execute multiple pipelines in a single request. You will notice that there are two different requests using the `pollsSeenEver` row source, one for the quantitative NPS question and one for the qualitative NPS question. 

Each pipeline returns all responses over the poll's lifetime and we then isolate the `visitorId`, `accountId`, responses, and response times using the `select` operator. `select` simply specifies which pieces of the row source's output are of interest and allows for field names to be specified. 

The output rows for these independent requests are then combined using `join`. In this case, the request looks for matching `visitorId` values and combines rows that with identical values.

### PII and visitorId

The provided request body contains a simple hash of the visitorId:
```
{"eval":{"visitorId": "hash(visitorId)"}},
```
You can remove this line in its entirety if you don't have a need to obscure or encode it.
