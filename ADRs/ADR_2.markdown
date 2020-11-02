# 2. A Message Queuing service is to be used to subscribe to events and updates via (Amazon Simple Queue Service) SQS 

## Status
Accepted

## Context
![Image of Context](https://github.com/sebfault/architecure-kata-sandbox/blob/master/ADRs/images/imageSource2.PNG)

## Decision

Depending on the API of the smart fridges and stores, 2 options are possible:
a. Smart fridges push the updates -> in this case events are to be added to a queueing service (SQS in AWS world). Events will trigger lambdas that will transform  data into domain objects and invoke internal lambdas responsible for handling events from fridge.
b. In the event if fridges require an outside cron job to pull event data, there can be an ClouWatch (or other cloud based cron job implementation), invoking pull from the fridges on a given schedule and invoke the lambdas converting events into internal domain model and invoking internal lambdas.

## Consequence
Should there be several types of integration, with both pull and push type for event retrieval, still the same set of lambdas can be triggered through either CloudWatch or SQS and pass the data over to the internal lambda set through Fridge API

